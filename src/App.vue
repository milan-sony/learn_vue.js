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
        jobLocation: []
      }
    }
  },
  methods: {

  }
}

</script>

<style></style>
