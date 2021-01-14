<template>
  <div class="user-profile">
    <div class= "user-profile_user-panel">
      <h1 class="user-profile_user-name">@{{user.username}}></h1>
      <div class="user-profile_follower-count">
        <strong>Followers:</strong>{{followers}}
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
        isAdmin: true
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

h1{
  margin:0;
}

</style>
