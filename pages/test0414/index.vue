<template>
  <main>
    <h1>Home page</h1>
    <div id="app" class="static" v-bind:class="{ active: isActive,'text-danger': hasError }" style="width:200px;height:200px">hi vue <br>text（字體） danger(紅色) </div>
    <div v-bind:class="classObject">2.class object with computed</div>
    <div v-bind:class="[activeClass, errorClass]">3.activeClass and errorClass</div>
    <div v-bind:class="[isActive ? activeClass : '', errorClass]">4.if "is active"==true will have a skyblue background</div>
    <div v-bind:class="[{ active: isActive }, errorClass]">5.to simply 4 while having multiple conditional classes</div>
    <mycomponent class="baz boo"></mycomponent> 
    <test-com></test-com>
    <div v-bind:style="{ color: activeColor, fontSize: fontSize + 'px' }">7.v-bind for css style</div>
    <div v-bind:style="styleObject">8.style object</div>
    <div v-bind:style="{ display: ['-webkit-box', '-ms-flexbox', 'flex'] }">9.Multiple Values</div>
    <div v-bind:style="[baseStyles, overridingStyles]">10.array value</div>
    <button v-on:click="location.href='https://www.w3school.com.cn/index.html' ;warn('Form cannot be submitted yet.', $event)">
      Submit</button>
  </main>
</template>
<script>
  import Vue from "vue"
  import TestCom from "@/components/TestCom.vue"
  import NavBar from "@/components/NavBar.vue"
   Vue.component('mycomponent', {
        template: '<p class="foo bar">Hi</p>'
   })
  export default{
      data(){
        return{
          //isActive:true,
          hasError:true,
          error:null,
          activeClass: 'active',
          errorClass: 'text-danger',
          activeColor: 'pink',
          fontSize: 30,
          styleObject: {
            color: 'red',
            fontSize: '13px',
            background: 'lightblue',
          },
          baseStyles:{
            background:'lightgreen',
          },
          overridingStyles:{
            fontSize:'20px',
            color:'lightblue',
            
          },
        }
      },
      computed:{
          classObject(){
            return{
              active:this.isActive, 
              'text-danger':this.error&&this.error.type==='fatal'
            }
          }
      },
      methods: {
        warn: function (message, event) {
          // 现在我们可以访问原生事件对象
         /* if (event) {
            event.preventDefault()
          }
          alert(message)*/
        }
      },
      components:{
        TestCom,
        NavBar
      }
  }
</script>

<style>
.active{background: skyblue;}
</style>
