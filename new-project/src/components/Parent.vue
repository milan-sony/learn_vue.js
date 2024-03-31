<template>

    <h2>Parent Component</h2>
    <div>
        <button @click="showChild = !showChild">Toggle Child</button>
        <ChildComponent v-if="showChild" />
    </div>

</template>

<script>

import ChildComponent from './Child.vue'

export default {
    name: 'ParentComponent',
    data() {
        return {
            showChild: true
        }
    },
    components: {
        ChildComponent
    },
    beforeCreate() {
        console.log('Parent beforeCreate()')
    },
    created() {
        console.log('Parent created()')
    },
    beforeMount() {
        console.log('Parent beforeMount()')
    },
    mounted() {
        console.log('Parent mounted()')
    },
    beforeUpdate() {
        console.log('Parent beforeUpdate()')
    },
    updated() {
        console.log('Parent updated()')
    },
    beforeUnmount(){
        console.log('Parent beforeUnmount()')
    },
    unmounted(){
        console.log('Parent unmounted()')
    }
}

</script>

<style></style>