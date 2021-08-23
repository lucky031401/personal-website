<template>
  <main>
    <h3>0601note</h3>
    <h5>1.輸入欄可以隨輸入同步顯示</h5>
    <input v-model="message" placeholder="text in smth">
    <p>your message: {{message}}</p>
    <h5>若想要等全部輸入後再更改值則"v-model"加上"加上".lazy"</h5>
    <input v-model.lazy="msg" placeholder="text in smth">
    <p>your message: {{msg}}</p>
    <h5>若想要限制輸入內容為數字則在"v-model"加上".number" type="number"</h5>
    <input v-model.number="age" type="number" placehoder="輸入年齡">
    <p>your message: {{age}}</p>
    <h5>2.勾選榜定事件</h5>
    <input type="checkbox" id="checkbox" v-model="checked">
    <label for="checkbox">(若被勾選則為true反之則為false):{{ checked }}</label>
    <h5>若想要用多個checkbox表示一個集合</h5>
    <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
    <label for="jack">Jack</label>
    <input type="checkbox" id="john" value="John" v-model="checkedNames">
    <label for="john">John</label>
    <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
    <label for="mike">Mike</label>
    <p>這些人有被勾選到： {{checkedNames}}</p>
    <p>使用v-for來寫多個checkbox項目</p>
    <div id="gender">
    <div>
          <span v-for="sub in subs">
            <input type="checkbox" :value="sub.item" v-model="subject"/>
            <label>{{sub.item}}</label>
          </span>
        </div>
        <div>選擇的科目是:{{subject}}</div>
    </div>
    <p>radio套件綁定</p>
    <div id="gender">
    <div>
      <span v-for="list in lists">
        <input type="radio" :value="list.name" v-model="food"/>
        <label>{{list.name}}</label>
      </span>
    </div>
    <div>選擇的食物是:{{food}}</div>
    <select v-model="selected" multiple>
      <option>A</option>
      <option>B</option>
      <option>C</option>
    </select>
    <br>
    <span>Selected: {{ selected }}</span>
</div>
  </main>
</template>
<script>
  export default{
    data(){
      return{
        message:"",
        checked :"",
        msg:"",
        age:"",
        msg_trim:"",
        food:"",
        subject:[],
        lists:[
          {name:"高麗菜"},
          {name:"芒果"},
          {name:"芋頭"}
        ],
        subs:[
          {val:"en",item:'英文'},
          {val:"ch",item:'國文'},
          {val:"math",item:'數學'}
        ],
        checkedNames:[],
        selected:[]
      }
    }
  }

</script>

<style>

</style>
