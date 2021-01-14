<template>
  <div class"user-profile">
    <div class "user-profile_user-panel"\>
      <h1 class="user-profile__user-name">@{{user.username}}></h1>
      <div class="user-profile__follower-count">
        <strong>Followers:</strong>{{followers}}
      </div>
    </div>
</template>

<script>
export default {
  name: 'UserProfile',
  
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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  min-height:100vh;
  background-color: #F3F5FA;

}

h1{
  margin:0;
}

</style>
