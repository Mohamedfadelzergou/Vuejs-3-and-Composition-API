<template>
        <h2>{{post.title}}</h2>
        <p>{{extract}}</p>
</template>

<script>
import { computed } from 'vue'
export default {
    props:['post'],
    setup(props){
        const extract = computed(()=>props.post.content.substring(0,50)+'...');
        return {extract}
    }
}
</script>

<style>

</style>