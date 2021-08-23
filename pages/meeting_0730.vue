<template>
  <main>   
      <nav-bar title="07.30 slots"></nav-bar>
      <div style="margin:1% 20% 1% 20%">
        <sub-title message="slots"></sub-title>
        <div style="margin:1.5%;padding:5px 0px 5px 0px">
          <span>除了以props將資料傳入組件(conponents)外，Vue也可以傳HTML進組件。</span>
          <br><br>
           <span style="font-size:10px">1.插入文字：在此範例中，插入"Press me"此文字</span>
          <br>
          <custom-button>Press me!</custom-button>
          <br><br>
          <span>2.插入html：這裡插入了span的tag(color:blue)以及"Your Profile"此段文字</span>
          <br>
          <nav-link url="/test0414"><span style="color:blue">Your Profile</span></nav-link>
          <span>3.替補內容：若在"slot" 中指定內容，若沒有額外輸入文字、則顯示預設內容</span><br>
          <submit-button>非預設文字</submit-button><br><br>
          <span>4.具名槽(named slots)：使一個conponent可以有不同名稱的槽，之後當我們在樣板中用組件時，可以使用slot屬性中指名某元素應被視為標頭槽，其餘會被當成無名槽</span><br>
          <base-layout>
            <template v-slot:header>
              <h1>Here might be a page title</h1>
            </template>

            <p>A paragraph for the main content.</p>
            <p>And another one.</p>

            <template v-slot:footer>
              <p>Here's some contact info</p>
            </template>
          </base-layout><br><br>
          <span>4.定域槽(scoped slots)：可以將資料傳回槽組件(slot component)，如此就能在父組件中得標註(markup)中存取組件資料</span><br>
          
        </div>
      </div>
  </main>
</template>
<script>
  import navbar from "@/components/NavBar.vue"
  import subtitle from "@/components/SubTitle.vue"
  import Vue from "vue"
  Vue.component('custom-button', {
        template: '<b-button variant="dark"><slot></slot></b-button>'
   });
  Vue.component('nav-link',{
        template:'<a v-bind:href="url" class="nav-link"><slot></slot></a>',
        props:['url'],
   })
   Vue.component('submit-button',{
        template:'<b-button variant="light"><slot>Submit</slot></b-button>'
   })
  Vue.component('base-layout',{
        template:'<div class="container"><header><slot name="header"></slot></header><main><slot></slot></main><footer><slot name="footer"></slot></footer></div>'
  })
  Vue.component('user-data',{
    template:'<div class="user"><slot :user="user></slot></div>',
    data:()=>({
      user:undefined
    }),
  })
  export default{
    data(){
      return{
        
      }
    },
    components:{
      navbar,
      subtitle,
    }
  }

</script>

<style>

</style>
