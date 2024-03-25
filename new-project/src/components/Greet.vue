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