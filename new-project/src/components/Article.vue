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