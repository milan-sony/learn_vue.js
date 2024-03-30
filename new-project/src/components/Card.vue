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