<template>
 <!-- 自构建的表单3 -->
    <div>
        <input :type="type" :value="inputValue" @input="inputHandler">
        <p>{{someValue}}</p>
    </div>
</template>

<script>
    export default {
        inject:['someValue'],//从App.vue中拿到的信息，provide提供过来的。
        props: {
            value: {
                type: String,
                default: ''
            },
            type: {
                type: String,
                default: 'text'
            }
        },
        data () {
            return {//单向数据流的原则：组件内不能修改props属性
                inputValue: this.value
            }
        },
        methods: {
            inputHandler(e) {
               this.inputValue = e.target.value
               //通知父亲组件值更新
               this.$emit('input',this.inputValue)

               //通知FormItem做校验
               //此处的$parent是父级FormItem.vue
               this.$parent.$emit('validate',this.inputValue)
            }
        },
    }
</script>

<style scoped>

</style>