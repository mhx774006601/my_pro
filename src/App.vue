<template>
  <div id="app">
    <p>
      <router-link :to="{name: 'pageA'}">pageA</router-link> |
      <!-- <router-link to="/a/1">参数1</router-link> |
      <router-link to="/a/2">参数2</router-link> | -->
      <router-link to="/b/3">pageB</router-link>
    </p>
   
    <p>
        <m-button @jiayou='handleClick'></m-button>
    </p>
    <router-view/>
    <router-view name="david"/>
    <p>
        <form-test></form-test>
    </p>
  </div>
</template>
<script>
import MButton from './views/Button'
import FormTest from './components/FormTest'
export default {
  //在此用provide提供一个信息，在其它组件中通过inject来拿到它。
  provide(){
    return{
      someValue:'来自祖先的信息'
    }
  },
   components:{
     MButton,
     FormTest,
   },
   methods: {
     handleClick(obj) {
       console.log(obj)
     }
   },
}
</script>


<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
