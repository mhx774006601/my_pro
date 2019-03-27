<template>
    <div>
        <button @click="handelClick"> 加油吧，亲</button>
    </div>
</template>

<script>
    export default {
        methods: {
            handelClick() {
                this.$emit('jiayou',{msg:'hello'})
            }
        },
    }
</script>

<style scoped>

</style>