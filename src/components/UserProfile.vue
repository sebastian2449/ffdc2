<template>
  <div class="user-profile">
    <div class= "user-profile_user-panel">
      <h1 class="user-profile_user-name">@{{user.username}}</h1>
      <div class="user-profile_admin-batch" v-if="user.isAdmin ">
        Admin
      </div>
      <div class="user-profile_admin-batch" v-else>
        Not Admin
      </div>
      <div class="user-profile_follower-count">
        <strong>Followers:</strong>{{followers}}
      </div>
    </div>
    <div class="user-profile_twoots-wrapper">
       <TwootItem v-for="twoot in user.twoots" :key="twoot.id" :username="user.username" :twoot="twoot"/>
    </div>
   </div>
</template>

<script>
export default {
  name: "UserProfile",
  
  data(){
    return{
      followers:0,
      user:{
        id:1,
        username:'sebastian2449 ',
        firstName: 'Sebastian',
        lastName: 'Vanegas Ruiz',
        email: 'sebastian2449@gmail.com',
        isAdmin: true,
        twoots:[
          {id:1,content:'This website is amazing'},
          {id:2,content:'Dont forget to suscribe'}
        ]
      }
    }
  },

  watch:{
    followers(newFollowerCount, oldFollowerCount){
      if(oldFollowerCount<newFollowerCount){
        console.log(`${this.user.username} has gain a follower`)
      }
    }
  },
  
  computed:{
    fullName(){
      return   this.user.firstName+' '+this.user.lastName;
    }
  },

  methods:{

    followUsers(){
      this.followers++
    }
  },

  mounted(){
    this.followUsers();
  }



}
</script>

<style>

.user-profile{
  display: grid;
  grid-template-columns: 1fr 3fr;
  width: 100%;
  padding:50px 5%;
}

.user-profile_user-panel{
  display: flex;
  flex-direction: column;
  margin-right: 50px;
  padding: 20px;
  background-color: white;
  border-radius: 5px;
  border: 1px solid #DFE3E8

}

.user-profile_admin-batch{
  background: coral;
  color: white;
  border-radius: 5px;
  margin-right: auto;
  padding: 0px 10px;
  font-weight: bold;
}


h1{
  margin:0;
}

</style>
