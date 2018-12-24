<template>
  <div class="users">
    <h1>Hello Users!</h1>
    <!-- 添加用户 -->
    <form  v-on:submit="addNew">
      <input type="text" placeholder="Enter name" v-model="newUser.name">
      <input type="text" placeholder="Enter email" v-model="newUser.email">
      <input type="submit" value="添加用户">
    </form>
    <!-- 展示用户 -->
    <ul>
      <li v-for="user in users">
        <input type="checkbox" class="toggle" v-model="user.contacted">
          <span :class="{contacted:user.contacted}">
            {{user.name}}: {{user.email}}
            <button v-on:click="deletUser">x</button>
        </span>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name:"users",
    data(){
      return {
        newUser:{},
        users:[
          {
            name:"Herry Lime",
            email:'Herry@163.com',
            contacted:false
          },
          {
            name:"Letme Lime",
            email:'Letme@163.com',
            contacted:false
          },
          {
            name:"Lucy Lime",
            email:'Lucy@163.com',
            contacted:false
          }
        ]
      }
    },  
    methods:{
       addNew:function(e){
        this.users.push({
          name:this.newUser.name,
          email:this.newUser.email,
          contacted:false
        });
       e.preventDefault();
       },
       deletUser:function(user){
        this.users.splice(this.users.indexOf(user),1);
       }
      }
  }
</script>

<style scoped>
  .contacted{
    text-decoration: line-through;
  }
</style>