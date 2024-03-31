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