# Vue.JS

- Text can be bind inside the template using the **mustache syntax** `{{ name }}` or using `v-directives`
    
    ```
    <template>
      <div>{{ greetings }}</div>
      <div v-text="name"></div>
    </template>
    
    <script>
    export default {
      name: "App",
      data(){
        return{
          greetings: "Hello",
          name: "MilanSony"
        }
      }
    }
    </script>
    
    <style>
    
    </style>
    
    ```
    
- `directive`
    - Directives in Vue.js are special attributes that are prefixed with the letter v. They are used to tell the Vue.js library to do something to the DOM element to which they are attached
    - Directives are **used to modify the behavior of our HTML elements which reside in the DOM**
- **Different directives** [link](https://vuejs.org/api/built-in-directives.html#built-in-directives)
- `v-text`
    - The v-bind shorthand property is `:`
    
    ```jsx
    <template>
    
      <div>{{ greetings }}</div>
      <div v-text="name"></div>
    
      <div v-bind:id="headingId">Heading</div>
      <button v-bind:disabled="isDisabled">Button</button>
    
      <h1 class="underline">Text Underline</h1>
      <h1 v-bind:class="status">Text Underline</h1>
      <h1 class="underline" v-bind:class="status">Text Underline</h1>
      <h1 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h1>
      <h1 v-bind:class="isSoldout ? 'sold-out' : 'new'">Sold out movie</h1>
      <h1 v-bind:class="['new', 'promoted']">New Movie</h1>
      <h1 v-bind:class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">Array condition movie</h1>
      <h1 v-bind:class="{
        // key : class name, value : condition
        promoted: isPromoted,
        new: !isSoldout,
        'sold-out': isSoldout
      }">Object condition movie</h1>
    
      <h2 v-bind:style="{
        // key : css property value : data property/condition
        color: highlightColor,
        'font-size': headerSize,
        'padding': '20px'
      }">Inline style</h2>
    
      <h2 v-bind:style="headerStyleObj">Style Object</h2>
      <h2 v-bind:style="[headerStyleObj, newStyleObj]">Style array object</h2>
      <h2 :style="headerStyleObj">v-bind shorthand</h2>
    
    </template>
    
    <script>
    
    export default {
      name: "App",
      data() {
        return {
          greetings: "Hello",
          name: "MilanSony",
          headingId: 'ID',
          isDisabled: true,
          status: 'danger',
          isPromoted: true,
          isSoldout: false,
          highlightColor: 'orange',
          headerSize: '50px',
          headerStyleObj: {
            color: 'Blue',
            'font-size' : '30px',
            padding: '10px'
          },
          newStyleObj:{
            'font-size': '40px',
            'background-color': 'yellow'
          }
        }
      }
    }
    
    </script>
    
    <style>
    .underline {
      text-decoration: underline;
    }
    
    .promoted {
      font-style: italic;
    }
    
    .new {
      color: green;
    }
    
    .sold-out {
      color: red;
    }
    </style>
    
    ```
    
- `v-bind` [link1](https://vuejs.org/api/built-in-directives.html#v-bind) [link2](https://www.w3schools.com/vue/vue_v-bind.php)
    - The shorthand of v-bind is `:`
    - The v-bind directive lets us bind an HTML attribute to data in the Vue instance. This makes it easy to change the attribute value dynamically.
- `v-if` and `v-else`
    
    ```jsx
    <template>
    
      <h2 v-if="num === 0">The number is Zero</h2>
      <h2 v-else>The number is not Zero</h2>
    
    </template>
    
    <script>
    
    export default {
      name: "App",
      data() {
        return {
          num: 5
        }
      }
    }
    
    </script>
    
    <style>
    
    </style>
    
    ```
    
- `v-else-if`
- wrapping the content (`template` tag)
    
    ```jsx
    <template>
    
      <h2 v-if="num === 0">The number is Zero</h2>
      <h2 v-else>The number is not Zero</h2>
    
      <div v-if="display">
        <p>Inside div tag</p>
        <h2>Name: Milan Sony</h2>
        <h2>Age: 23</h2>
      </div>
    
      <template v-if="display">
        <p>No div tag its inside template tag</p>
        <p>The template tag acts as an invisible wrapper</p>
        <h2>Name: Milan Sony</h2>
        <h2>Age: 23</h2>
      </template>
    
    </template>
    
    <script>
    
    export default {
      name: "App",
      data() {
        return {
          num: 5,
          display: true
        }
      }
    }
    
    </script>
    
    <style></style>
    
    ```
    
- `v-show` [link](https://www.w3schools.com/vue/vue_v-show.php)
    - The v-show directive hides an element when the condition is 'false' by setting the CSS 'display' property value to 'none'
    - The difference between `v-show` and `v-if` is that `v-if` creates (renders) the element depending on the condition, but with `v-show` the element is already created, `v-show` only changes its visibility
- `v-for`
    - [link](https://vuejs.org/api/built-in-directives.html#v-for)
    
    ```jsx
    <template>
    
      <h2 v-for="name in names" :key="name">{{ name }}</h2>
      <h2 v-for="(name, index) in names" :key="name">{{index}} {{ name }}</h2>
      <h2 v-for="(name, index) in names" :key="name">{{index + 1}} {{ name }}</h2>
    
    </template>
    
    <script>
    
    export default {
      name: "App",
      data() {
        return {
          names: ['milan', 'sony']
        }
      }
    }
    
    </script>
    
    <style></style>
    
    ```
    
- `v-on` (event handler) [link](https://www.w3schools.com/vue/vue_v-on.php)
    - The shorthand property for v-on is `@`
    - `@click.self` is used to add the click event only to that particular element
    - inline event handlers
        
        ```jsx
        <template>
        
          <h2>{{ name }}</h2>
          <div>
            <button v-on:click="name = 'sony'">Change name</button>
          </div>
        
        </template>
        
        <script>
        
        export default {
          name: "App",
          data() {
            return {
              name: 'milan'
            }
          },
          methods:{
        
          }
        }
        
        </script>
        
        <style></style>
        
        ```
        
    - inline count increment and decrement
        
        ```jsx
        <template>
        
          <h2>{{ name }}</h2>
          <div>
            <button v-on:click="name = 'sony'">Change name</button>
          </div>
        
          <h2>{{ count }}</h2>
          <div>
            <button v-on:click="count ++">Increment</button>
            <button v-on:click="count --">Decrement</button>
          </div>
        
        </template>
        
        <script>
        
        export default {
          name: "App",
          data() {
            return {
              name: 'milan',
              count: 0
            }
          },
          methods:{
        
          }
        }
        
        </script>
        
        <style></style>
        
        ```
        
    - onclick function call
        
        ```jsx
        <template>
        
          <h2>{{ name }}</h2>
          <div>
            <button v-on:click="name = 'sony'">Change name</button>
          </div>
        
          <h2>{{ count }}</h2>
          <div>
            <button v-on:click="increment()">Increment</button>
            <button v-on:click="decrement()">Decrement</button>
          </div>
        
        </template>
        
        <script>
        
        export default {
          name: "App",
          data() {
            return {
              name: 'milan',
              count: 0
            }
          },
          methods:{
            increment(){
              this.count ++
            },
            decrement(){
              this.count --
            }
          }
        }
        
        </script>
        
        <style></style>
        
        ```
        
    - on click pass value into the function
        
        ```
        <template>
        
          <h2>{{ name }}</h2>
          <div>
            <button v-on:click="name = 'sony'">Change name</button>
          </div>
        
          <h2>{{ count }}</h2>
          <div>
            <button v-on:click="increment(1)">Increment</button>
            <button v-on:click="decrement(1)">Decrement</button>
            <button v-on:click="increment(5)">Increment</button>
            <button v-on:click="decrement(5)">Decrement</button>
          </div>
        
        </template>
        
        <script>
        
        export default {
          name: "App",
          data() {
            return {
              name: 'milan',
              count: 0
            }
          },
          methods:{
            increment(num){
              this.count += num
            },
            decrement(num){
              this.count -= num
            }
          }
        }
        
        </script>
        
        <style></style>
        
        ```
        
    - multiple methods
        
        ```jsx
        <template>
        
          <h2>{{ name }}</h2>
          <div>
            <button @:click="changeName(), increment(1)">Change name</button>
          </div>
        
          <h2>{{ count }}</h2>
          <div>
            <button v-on:click="increment(1)">Increment</button>
            <button v-on:click="decrement(1)">Decrement</button>
            <button v-on:click="increment(5)">Increment</button>
            <button v-on:click="decrement(5)">Decrement</button>
          </div>
        
        </template>
        
        <script>
        
        export default {
          name: "App",
          data() {
            return {
              name: 'milan',
              count: 0
            }
          },
          methods:{
            changeName(){
              this.name = "Sony"
            },
            increment(num){
              this.count += num
            },
            decrement(num){
              this.count -= num
            }
          }
        }
        
        </script>
        
        <style></style>
        
        ```
        
- `v-model` form handling
    - v-model and form handling [link](https://vuejs.org/guide/essentials/forms.html#form-input-bindings)
        
        ```jsx
        <template>
        
          <pre>
            {{ JSON.stringify(formValue, null, 2) }}
          </pre>
        
          <form @submit="submitForm">
        
            <div>
              <p>Name</p>
              <input type="text" id="name" v-model="formValue.name">
            </div>
        
            <div>
              <p>Profile Summary</p>
              <textarea id="profile" cols="30" rows="10" v-model="formValue.profileSummary"></textarea>
            </div>
        
            <div>
              <p>Country</p>
              <select id="country" v-model="formValue.country">
                <option value="">Select a country</option>
                <option value="india">India</option>
                <option value="china">China</option>
              </select>
            </div>
        
            <div>
              <p>Job Location</p>
              <select id="job-location" multiple v-model="formValue.jobLocation">
                <option value="india">India</option>
                <option value="china">China</option>
              </select>
            </div>
        
            <div>
              <input type="checkbox" id="remotework" v-model="formValue.remoteWork" true-value = 'yes' false-value = 'no'>
              <span>Open to remote work?</span>
            </div>
        
            <div>
              <p>Skills</p>
              <input type="checkbox" id="html" value="html" v-model="formValue.skillset"><span>HTML</span>
              <input type="checkbox" id="css" value="css" v-model="formValue.skillset"><span>CSS</span>
              <input type="checkbox" id="javascript" value="javascript" v-model="formValue.skillset"><span>JavaScript</span>
            </div>
            <div>
        
              <p>Years of exprerience</p>
              <input type="radio" id="0-2" value="0-2" v-model="formValue.yearsOfExpreience"><span>0-2</span>
              <input type="radio" id="3-5" value="3-5" v-model="formValue.yearsOfExpreience"><span>3-5</span>
              <input type="radio" id="6-10" value="6-10" v-model="formValue.yearsOfExpreience"><span>6-10</span>
            </div>
        
            <div>
              <button>SUMBIT</button>
            </div>
        
          </form>
        
        </template>
        
        <script>
        
        export default {
          name: "App",
          data() {
            return {
              formValue: {
                name: '',
                profileSummary: '',
                country: '',
                jobLocation: [],
                remoteWork: 'no',
                skillset: [],
                yearsOfExpreience: ''
              }
            }
          },
          methods: {
            submitForm(event){
              event.preventDefault()
              console.log('Form Values', this.formValue)
            }
          }
        }
        
        </script>
        
        <style>
        
        </style>
        
        ```
        
- `methods` In Vue.js, a method is a function that is associated with a Vue instance. Methods are used to perform actions in response to user interaction or other events
    
    ```jsx
    <template>
    
      <h2>{{ 10 + 20 }}</h2>
    
      <h2>Add method {{ add() }}</h2>
    
    </template>
    
    <script>
    
    export default {
      name: "App",
      data() {
        return {
    
        }
      },
      methods:{
        add(){
          return 2+3+5
        }
      }
    
    }
    
    </script>
    
    <style></style>
    
    ```
    
    - passing value to the method/function
        
        ```jsx
        <template>
        
          <h2>{{ 10 + 20 }}</h2>
        
          <h2>Add method {{ add(2, 3, 5) }}</h2>
          <h2>Add method {{ add(2, 3, 2) }}</h2>
        
        </template>
        
        <script>
        
        export default {
          name: "App",
          data() {
            return {
        
            }
          },
          methods:{
            add(num1, num2, num3){
              return num1 + num2 + num3
            }
          }
        
        }
        
        </script>
        
        <style></style>
        
        ```
        
    - using this keyword
    - In vue when defining the methods don’t use arrow function
        
        ```jsx
        <template>
        
          <h2>{{ 10 + 20 }}</h2>
        
          <h2>Add method {{ add(2, 3, 5) }}</h2>
          <h2>Add method {{ add(2, 3, 2) }}</h2>
          <h2>multiply {{ multiply(5) }}</h2>
        
        </template>
        
        <script>
        
        export default {
          name: "App",
          data() {
            return {
              baseMultiplier:5
            }
          },
          methods:{
            add(num1, num2, num3){
              return num1 + num2 + num3
            },
            multiply(num){
              return num * this.baseMultiplier
            }
          }
        }
        
        </script>
        
        <style></style>
        
        ```
        
- `modifiers`: are the suffix that can be added either to the v-on directive or the v-model directive to add some functionality inline within the template
    - [trim](https://vuejs.org/guide/essentials/forms.html#trim) If you want whitespace from user input to be trimmed automatically, you can add the `trim` modifier to your `v-model`-managed inputs:
        
        ```jsx
        <input v-model.trim="msg" />
        ```
        
    - [number](https://vuejs.org/guide/essentials/forms.html#number) If you want user input to be automatically typecast as a number, you can add the `number` modifier to your `v-model` managed inputs:
        
        ```jsx
        <input v-model.number="age" />
        ```
        
    - [lazy](https://vuejs.org/guide/essentials/forms.html#lazy)
        
        ```jsx
        <!-- synced after "change" instead of "input" -->
        <input v-model.lazy="msg" />
        ```
        
        - event modifier [link](https://vuejs.org/guide/essentials/event-handling.html#event-modifiers)
            - `.prevent` - <form @submit.prevent="submitForm"> use this instead of event.preventDefault()
            - key modifier [link](https://vuejs.org/guide/essentials/event-handling.html#key-modifiers)
            
            ```jsx
            <!-- only call `submit` when the `key` is `Enter` -->
            <input @keyup.enter="submit" />
            ```
            
- `computed properties` [link](https://vuejs.org/guide/essentials/computed.html)
    - computed properties are **cached** based on their reactive dependencies. A computed property will only re-evaluate when some of its reactive dependencies have changed.
    - Computed will only recalculate every time its dependent variables change, and methods will be computed whenever it is called
    - Computed properties and methods are two ways to define functions in Vue.js. They are both used to perform calculations or logic, but they have different use cases.
    - Computed properties are used to calculate values that are based on other data in the component. They are cached, meaning that they are only recalculated when their dependencies change. This makes them ideal for values that are used frequently in the template, such as the total price of a cart or the number of items in a list.
    - Methods are used to perform actions that can be triggered by events, such as clicking a button or submitting a form. They can also be used to perform complex calculations that are not needed every time the template is rendered.
    
    ```jsx
    <template>
    
      <h2>Fullname: {{ firstName }} {{ lastName }}</h2>
      <h2>Computed fullname: {{ fullName }}</h2>
    
      <h2>Computed total: {{ total }}</h2>
      <h2>Method Total: {{ getTotal() }}</h2>
      <input type="text" v-model="country">
    
    </template>
    
    <script>
    
    export default {
      name: "App",
      data() {
        return {
          firstName: 'Milan',
          lastName: 'Sony',
          items: [
            {
              id: 1,
              title: 'TV',
              price: 100
            },
            {
              id: 2,
              title: 'Phone',
              price: 200
            },
            {
              id: 3,
              title: 'Laptop',
              price: 300
            },
          ],
          country: ''
        }
      },
      methods: {
        getTotal(){
          console.log('getTotal()')
          return this.items.reduce((total, curr) => (total = total + curr.price), 0)
        }
    
      },
      computed:{
        fullName(){
          return `${this.firstName} ${this.lastName}`
        },
        total(){
          console.log('total()')
          return this.items.reduce((total, curr) => (total = total + curr.price), 0)
        }
      }
    }
    
    </script>
    
    <style>
    
    </style>
    
    ```
    
    - list of items computed properties
    
    ```jsx
    <template>
    
      <h2>Fullname: {{ firstName }} {{ lastName }}</h2>
      <h2>Computed fullname: {{ fullName }}</h2>
    
      <h2>Computed total: {{ total }}</h2>
      <h2>Method Total: {{ getTotal() }}</h2>
      <input type="text" v-model="country">
    
      <template v-for="item in items" :key="item.id">
        <h2 v-if="item.price > 100">{{ item.title }} {{ item.price }}</h2>
      </template>
    
      <!-- instead for the above written we can use the computed property -->
      <h2 v-for="item in expensiveItems" :key="item.id">{{ item.title }} {{ item.price }}</h2>
    
    </template>
    
    <script>
    
    export default {
      name: "App",
      data() {
        return {
          firstName: 'Milan',
          lastName: 'Sony',
          items: [
            {
              id: 1,
              title: 'TV',
              price: 100
            },
            {
              id: 2,
              title: 'Phone',
              price: 200
            },
            {
              id: 3,
              title: 'Laptop',
              price: 300
            },
          ],
          country: ''
        }
      },
      methods: {
        getTotal(){
          console.log('getTotal()')
          return this.items.reduce((total, curr) => (total = total + curr.price), 0)
        }
    
      },
      computed:{
        fullName(){
          return `${this.firstName} ${this.lastName}`
        },
        total(){
          console.log('total()')
          return this.items.reduce((total, curr) => (total = total + curr.price), 0)
        },
        expensiveItems(){
          return this.items.filter(item => item.price > 100)
        }
      }
    }
    
    </script>
    
    <style>
    
    </style>
    
    ```
    
- computed `getter` and `setter` [link](https://vuejs.org/guide/essentials/computed.html#writable-computed)
    
    Computed properties are by default getter-only. If you attempt to assign a new value to a computed property, you will receive a runtime warning. In the rare cases where you need a "writable" computed property, you can create one by providing both a getter and a setter:
    
    ```jsx
    <template>
    
      <h2>Fullname: {{ firstName }} {{ lastName }}</h2>
      <h2>Computed fullname: {{ fullName }}</h2>
      <button @click="changeFullName">Change Name</button>
    
    </template>
    
    <script>
    
    export default {
      name: "App",
      data() {
        return {
          firstName: 'Milan',
          lastName: 'Sony',
        }
      },
      methods: {
        changeFullName(){
          this.fullName = 'Milosh Sony'
        }
      },
      computed:{
        fullName:{
          // getter : read computed property value
          get(){
            return `${this.firstName} ${this.lastName}`
          },
          // setter : set() is called when new value is assigned into the computed property
          set(value){
            const names = value.split(' ')
            this.firstName = names[0]
            this.lastName = names[1]
          }
        }
      }
    }
    
    </script>
    
    <style>
    
    </style>
    
    ```
    
- `watchers` [link1](https://vuejs.org/guide/essentials/watchers.html#watchers) [link2](https://www.w3schools.com/vue/vue_watchers.php)
    - Watchers allow you to observe a property in Vue.js and trigger a method when it changes.
    - This is same as of computed property but different:
        - Here are some use cases:
        - Computed properties are used to calculate the value of a property based on some other conditions. Watchers, on the other hand, are not primarily used for changing the value of a property; instead, they are used to notify you when the value has changed and let you perform certain actions based on these changes.
        - watchers should be used when you need to be notified when a specific data property changes and react accordingly. Methods should be used when you need to perform an action, such as updating data properties, calling other methods, or interacting with the DOM.
        - can be used when you need to add some transitions
        - can be used when you have to call an API in response to change in application data
        - In addition to the new property value, the previous property value is also automatically available as an input argument to watcher methods.
    
    ```jsx
    <template>
    
      <h2>Volume Tracker (0-20)</h2>
      <h2>Current Volume {{ volume }}</h2>
      <div>
        <button @click="volume += 2">Increase</button>
        <button @click="volume -= 2">Decrease</button>
      </div>
    
    </template>
    
    <script>
    
    export default {
      name: "App",
      data() {
        return {
          volume: 0
        }
      },
      methods: {
    
      },
      computed: {
    
      },
      watch: {
        volume(newValue, oldValue) {
          if (newValue > oldValue && newValue === 16) {
            alert("Volume above 16")
          }
        }
      }
    }
    
    </script>
    
    <style></style>
    
    ```
    
- `immediate` (watchers)
    
    The immediate property will runs the watcher handler on page load
    
    ```jsx
    <template>
    
      <h2>Volume Tracker (0-20)</h2>
      <h2>Current Volume {{ volume }}</h2>
      <div>
        <button @click="volume += 2">Increase</button>
        <button @click="volume -= 2">Decrease</button>
      </div>
      <input type="text" v-model="movie">
    
    </template>
    
    <script>
    
    export default {
      name: "App",
      data() {
        return {
          volume: 0,
          movie: 'Batman'
        }
      },
      methods: {
    
      },
      computed: {
    
      },
      watch: {
        volume(newValue, oldValue) {
          if (newValue > oldValue && newValue === 16) {
            alert("Volume above 16")
          }
        },
        movie:{
          handler(newValue){
            console.log(`Calling an API with the movie name = ${newValue}`)
          },
          immediate: true
        }
      }
    }
    
    </script>
    
    <style></style>
    
    ```
    
- `deep watcher` [link](https://vuejs.org/guide/essentials/watchers.html#deep-watchers)

---

- `components` [link](https://vuejs.org/guide/essentials/component-basics#components-basics)
    - Components are reusable Vue instances with custom HTML elements. Components can be reused as many times as you want or used in another component, making it a child component
- **point to remember**
    - In Single File Component’s (SFC), it's recommended to use `PascalCase` tag names for child components
- `component props` component props (props) are custom attributes that can register on a component which allow the component content to be dynamic
- `props` [link](https://vuejs.org/guide/essentials/component-basics#passing-props) props is an array of all data properties or custom attributes that the component will accept from the parent component. Declared props are automatically exposed to the template
    - E.g. App.vue (parent)
        
        ```jsx
        <template>
          <GreetMe name="Milan" />
          <GreetMe :name="name" :email="email" />
        </template>
        
        <script>
        import GreetMe from './components/Greet.vue'
        
        export default {
          name: 'App',
          components: {
            GreetMe
          },
          data() {
            return {
              name: 'milosh',
              email: 'milosh@gmail.com'
            }
          }
        }
        </script>
        
        <style></style>
        
        ```
        
    - Greet.vue (child)
        
        ```jsx
        <template>
            <h2>Hello {{ name }} Email: {{ email }}</h2>
        </template>
        
        <script>
        export default {
            name: 'GreetMe',
            props: [
                'name',
                'email'
            ]
        }
        </script>
        ```
        
- **prop types and validations** (`props as an object`) [link](https://www.w3schools.com/vue/vue_props.php)
    - When the `props` option is given as an object several options can be defined in addition to the prop names:
        
        App.vue (parent)
        
        ```jsx
        <template>
          <!-- <GreetMe name="Milan" />
          <GreetMe :name="name" :email="email" /> -->
        
          <ArticleList title="Article" :likes="50" :isPublished="true" />
        </template>
        
        <script>
        // import GreetMe from './components/Greet.vue'
        import ArticleList from './components/Article.vue'
        
        export default {
          name: 'App',
          components: {
            // GreetMe,
            ArticleList
          },
          data() {
            return {
              name: 'milosh',
              email: 'milosh@gmail.com'
            }
          }
        }
        </script>
        
        <style></style>
        
        ```
        
        Article.vue (child)
        
        ```jsx
        <template>
            <h2>Article Component</h2>
            <h3>{{ title }}</h3>
            <h4>likes: {{ likes }}</h4>
            <p>Publised {{ isPublished ? 'Yes' : 'No' }}</p>
        </template>
        
        <script>
        export default {
            name: 'ArticleList',
            props: {
                title:{
                    type: String,
                    required: true,
                    default: 'Article default title'
                },
                likes: Number,
                isPublished: Boolean
            },
        }
        </script>
        
        <style></style>
        ```
        
- no prop attributes
    - A non-prop attribute in Vue.js is an attribute that is passed to a component but does not have a corresponding prop defined in the component's options. Non-prop attributes are typically used to pass HTML attributes, such as class, style, and id, to a component
- **provide/inject** (props drilling or nested components) [link1](https://www.w3schools.com/vue/vue_provide-inject.php) [link2](https://vuejs.org/guide/components/provide-inject)
    - Provide/Inject in Vue is used to provide data from one component to other components, particularly in large projects.
    - Provide/Inject is a way to share data as an alternative to passing data using props
    - `Provide` makes data available to other components
    - `Inject` is used to get the provided data
    - If we use provide/inject instead of props, we only need to define the provided data where it is provided, and we only need to define the injected data where it is injected
    - **Note**:
        - If you want to utilize the property only further down in the component tree you can specify the provide as an object
        - If the data has to be used in the same component as well as components down in the component tree you can specify the provide as a function which returns an object
- **component event** (`$emit()`) [link](https://www.w3schools.com/vue/vue_emit.php)
    - With the built-in **`$emit()`** method in Vue we can create a custom event in the child component that can be captured in the parent element
    - `Props` are used to send data from the parent element to the child component, and **`$emit()`** is used to do the opposite: to pass information from the child component to the parent
    - E.g.
        
        Popup.vue - on click on the close button we are emitting a custom event called close (we can give any name) to the parent component
        
        ```jsx
        <template>
            <div>
                <h2>This is a popup</h2>
                <button @click="$emit('close')">close popup</button>
            </div>
        </template>
        
        <script>
        export default{
            name: 'PopUp',
            emits: ['close']
        }
        
        </script>
        
        <style>
        
        </style>
        ```
        
        App.vue - In the app component we need to listen to the close event (the custom event from the child component) for that we use the event binding (shorthand `@` ) and listen to own event `@close` and set Showpop to false `@close=”Showpopup = false”` 
        
        ```jsx
        <template>
        
          <button @click="showPopup = true">show popup</button>
          <PopUp v-show="showPopup" @close="showPopup = false" />
        
        </template>
        
        <script>
        
        import PopUp from './components/Popup.vue'
        
        export default {
          name: 'App',
          data() {
            return {
              showPopup: false
            }
          },
          components:{
            PopUp
          }
        }
        </script>
        
        <style></style>
        
        ```
        
    - You can also pass data from child component to parent component by including the data as the 2nd argument in the $emit()
- validating emitted event
- `slots` [link](https://www.w3schools.com/vue/vue_slots.php)
    - Slots allow a parent component to embed any content in a child component including HTML elements
    - `props` allow you to re-use components by passing in different data
    - Although props are great for re-usability, we do have a strict parent child relationship
    - The child will always be in control of the HTML content and the parent can only pass in different data values
    - Slots are more powerful, they allows you to re-use a component, they allows the parent component to control inside the child content
    - E.g.
        
        card.vue
        
        ```jsx
        <template>
            <div class="card">
                <slot>Default Content</slot>
            </div>
        </template>
        
        <script>
        export default{
            name: 'CardVue',
        
        }
        </script>
        
        <style scoped>
        
        .card{
            display: flex;
            justify-self: center;
            align-items: center;
            text-align: center;
            width: 180px;
            height: 60px;
            background-color: red;
            color: white;
            margin-bottom: 20px;
        }
        
        </style>
        ```
        
        App.vue
        
        ```jsx
        <template>
          <CardVue></CardVue>
          <CardVue>hello</CardVue>
          <CardVue><h1>Milan Sony</h1></CardVue>
        </template>
        
        <script>
        
        import CardVue from './components/Card.vue'
        
        export default {
          name: 'App',
          data() {
            return {
            }
          },
          components: {
            CardVue
          },
          methods: {
        
          }
        }
        
        </script>
        
        <style></style>
        
        ```
        
- `v-slot` [link](https://www.w3schools.com/vue/vue_v-slot.php) (named slots)
- **Dynamic Component** [link](https://www.w3schools.com/vue/vue_dynamic-components.php)
    - Dynamic Components can be used to flip through pages within your page, like tabs in your browser, with the use of the 'is' attribute
    - To make a dynamic component we use the `<component>` tag to represent the active component. The 'is' attribute is tied to a value with `v-bind`, and we change that value to the name of the component we want to have active
    - E.g.
        
        ```jsx
        <template>
          <button @click="activeTab = 'TabA'">Tab A</button>
          <button @click="activeTab = 'TabB'">Tab B</button>
          <button @click="activeTab = 'TabC'">Tab C</button>
        
          <component :is="activeTab"/>
        
          <!-- <div>
            <TabA v-if="activeTab === 'TabA'" />
            <TabB v-if="activeTab === 'TabB'" />
            <TabC v-if="activeTab === 'TabC'" />
          </div> -->
        
        </template>
        
        <script>
        
        import TabA from './components/TabA.vue'
        import TabB from './components/TabB.vue'
        import TabC from './components/TabC.vue'
        
        export default {
          name: 'App',
          data() {
            return {
              activeTab: 'TabA'
            }
          },
          components: {
            TabA,
            TabB,
            TabC
          },
          methods: {
        
          }
        }
        
        </script>
        
        <style></style>
        
        ```
        
    - `<KeepAlive>`
    - `include` or `exclude` attributes on the `<KeepAlive>` tag
        
        *click on the [link](https://www.w3schools.com/vue/vue_dynamic-components.php) to read more about `<KeepAlive>` and `include` or `exclude` attributes on the `<KeepAlive>` tag*
        
- **Teleport** [link](https://www.w3schools.com/vue/vue_teleport.php)
    - To move some content to somewhere else in the DOM structure we use the Vue `<Teleport>` tag around the content and the 'to' attribute to define where to move it
    - used in pop up modals
- Vue HTTP request [link](https://www.w3schools.com/vue/vue_http.php)
    - E.g.
        
        GetData.vue
        
        1st install `axios` `npm install axios`
        
        (add this component in the App.vue)
        
        ```jsx
        <template>
        
            <div>
                <button @click="fetchData">Load Data</button>
            </div>
        
            <div v-if="data">
                <pre>{{ data.first_name + " " + data.last_name }}</pre>
                <p>"{{ data.employment.title }}"</p>
            </div>
        
        </template>
        
        <script>
        
        import axios from 'axios'
        
        export default {
            name: 'PostList',
            data() {
                return {
                    data: ''
                }
            },
            methods: {
                async fetchData() {
                    await axios.get("https://random-data-api.com/api/v2/users").then((response)=>{
                        console.log(response.data)
                        this.data = response.data
                    }).catch((err)=>{
                        console.log(err)
                    })
                }
            }
        }
        
        </script>
        
        <style></style>
        ```
        
- **Lifecycle Hooks** [link](https://www.w3schools.com/vue/vue_lifecycle-hooks.php)
    - use - sometimes we need to get the data from the API or something not only when the button is clicked but also the app loads in the browser. E.g. If you navigate to your profile page within an application your profile data need to be rendered in the browser without the need of a button click this is where the lifecycle method come in use
- GET request on page load
    
    To get data on page load we need to call the get data function (API function) inside the `created()` lifecycle
    
    ```jsx
    <template>
    
        <div v-if="data">
            <pre>{{ data.first_name + " " + data.last_name }}</pre>
            <p>"{{ data.employment.title }}"</p>
        </div>
    
    </template>
    
    <script>
    
    import axios from 'axios'
    
    export default {
        name: 'GetData',
        data() {
            return {
                data: ''
            }
        },
        created() {
            this.fetchData()
        },
        methods: {
            async fetchData() {
                await axios.get("https://random-data-api.com/api/v2/users").then((response) => {
                    console.log(response.data)
                    this.data = response.data
                }).catch((err) => {
                    console.log(err)
                })
            }
        }
    }
    
    </script>
    
    <style></style>
    ```
    
- **Template Refs** [link](https://www.w3schools.com/vue/vue_refs.php)
    - Vue **Template Refs** are used to refer to specific DOM elements
    - When the **`ref`** attribute is set on an HTML tag, the resulting DOM element is added to the **`$refs`** object
    - We can use the **`ref`** attribute and the **`$refs`** object in Vue as an alternative to methods in plain JavaScript like getElementById() or querySelector()
        - E.g.
            
            ```jsx
            <template>
                <div>
                    <input type="text" ref="inputRef">
                    <p ref="p1">Click the button to copy this text into the paragraph below.</p>
                    <button @click="transferText">Transfer text</button>
                    <p ref="p2">...</p>
                </div>
            </template>
            
            <script>
            export default {
                name: 'TemplateRef',
                mounted() {
                    this.$refs.inputRef.focus()
                },
                methods: {
                    transferText() {
                        this.$refs.p2.innerHTML = this.$refs.p1.innerHTML;
                    },
                }
            }
            </script>
            
            <style scoped></style>
            ```
