<template>
  <div class="home">
    <h1 ref="header">Hello</h1>
    <p>Mon Name:{{name}} | Age: {{age}}</p>
    <button @click="sayHello">Welcome</button>
    <hr>
    <input type="text" v-model="search">
    <p>{{search}}</p>
    <div v-for="coures in result">{{coures}}</div>
    <hr>
    <button @click="handleWatch">stop</button>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import {ref,computed,watch, watchEffect} from 'vue'
export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  setup(){
    let header =ref(null);
    let name="mohamed fadel zergou";
    let age = 22;
    let personne={
      name:"saleh zergou",
      age:15
    };
    const search=ref('');
    const courses=ref(['angular','reactjs','vuejs','laravel','seo']);
    //computed
    const result=computed(()=>{
      return courses.value.filter(course => course.includes(search.value));
    });
    //watch
    const stopWatch = watch(search,()=>{
      console.log(search.value)
    });
    const stopWatchEffect = watchEffect(()=>{
      console.log('watchEffect',search.value)
    });
    //method
    const sayHello = () => {
      console.log(header.value)
      header.value.classList.add('my-2')
      header.value.textContent="Welcome To MFZ WEB"
      }
    handleWatch = () => {
      stopWatch()
      stopWatchEffect()
    }
    return {name,age,sayHello,header,personne,courses,search,result,handleWatch}

  }
}
</script>
