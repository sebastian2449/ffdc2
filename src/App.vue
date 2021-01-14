<template>
    <div id="app">
        <user-profile/>
    </div>
</template>

<script>

import UserProfile from "./components/UserProfile";

export default {
    name:'App',
    components:{UserProfile}
}
</script>

<style>
#app{
    font-family: Avenir, Helvetica, Arial, Helvetica, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    min-height: 100vh;
    background-color: #F3F5FA;
}

</style>

