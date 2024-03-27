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