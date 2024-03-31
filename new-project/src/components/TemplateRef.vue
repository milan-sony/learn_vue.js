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