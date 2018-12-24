<template>
  <div class="test">
    <!-- 获取数据 -->
    <h1>{{title}}</h1>
    <p>{{user.firstName}}</p>
    <p v-text="user.lastName"></p>
    <!-- v-if 与 v-else-->
    <p v-if="showName">{{user.firstName}}</p>
    <p v-else>Nobady</p>
    <!-- v-for -->
    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>
    <!-- v-on -->
    <button v-on:click="greet">say something</button>
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
    <hr>
    <!-- computed 计算属性 -->
    <label>firstName:</label>
    <input type="text" v-model="user.firstName">
    <br>
    <label>lastName:</label>
    <input type="text" v-model="user.lastName">
    <br>
    <h3>{{Name}}</h3>
    <!-- props属性 -->
    <h2>{{msg}}</h2>
  </div>
</template>

<script>
  export default {
    name:"test",
    props:{
      msg:{
        type:String,
        default:"默认就是这些值"
      }
    },
    data(){
      return {
        title:"Hello Vue.js!",
        user:{
          firstName:"heimeizai",
          lastName:"sanShu"
        },
        showName:false,
        items:[
          {title:"item1"},
          {title:"item2"},
          {title:"item3"},
          {title:"item4"}
        ]
      }
    },
    methods:{
        greet:function(){
          alert("Hello Wrold!");
        },
        pressKey:function(){
          console.log("an");
        },
        enterHit:function(){
          console.log("en");
        }
      },
    computed:{
      Name:function(){
        return this.user.firstName + " " + this.user.lastName;
      }
    }
  }
</script>

<style scoped>
  
</style>