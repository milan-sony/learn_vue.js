<template>

  <pre>
    {{ JSON.stringify(formValue, null, 2) }}
  </pre>

  <form>

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

  }
}

</script>

<style>

</style>
