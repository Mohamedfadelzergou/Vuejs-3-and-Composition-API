<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/blog">Blog</router-link>|
    <router-link to="/about">About</router-link>
  </div>
  <div>
    <button @click="Previous">Previous</button>
    <button @click="Next">Next</button>
    <button @click="Redirect">Redirect</button>
  </div>
  <router-view/>
</template>
<script>
import { useRouter } from 'vue-router'
export default {
  setup() {
    const router = useRouter()
    const Previous =()=>{
     router.go(-1);
    }
    const Next =()=>{
      router.go(+1);
    }
    const Redirect =()=>{
      router.push('/blog');
    }
    return {Previous,Next,Redirect}
  },
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
