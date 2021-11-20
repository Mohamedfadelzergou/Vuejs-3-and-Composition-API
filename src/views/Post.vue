<template>
    <h1>List of Posts</h1>
    <div v-for="post in posts" :key="post.id">
        <one-post :post="post"/>
    </div>
</template>
<script>
import { ref } from 'vue'
import OnePost from '../components/OnePost.vue';
export default {
  components: { OnePost },
    setup(){
        const posts=ref([
            {
            "id": 1,
            "title": "Learn angular",
            "content": "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Blanditiis doloribus quis quam nulla, nihil dignissimos rerum, doloremque tempora perferendis est nostrum tempore corrupti libero commodi quae voluptate qui delectus voluptatum!"
            },
            {
            "id": 2,
            "title": "Learn Flutter",
            "content": "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Blanditiis doloribus quis quam nulla, nihil dignissimos rerum, doloremque tempora perferendis est nostrum tempore corrupti libero commodi quae voluptate qui delectus voluptatum!"
            },
            {
            "id": 3,
            "title": "Learn vuejs",
            "content": "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Blanditiis doloribus quis quam nulla, nihil dignissimos rerum, doloremque tempora perferendis est nostrum tempore corrupti libero commodi quae voluptate qui delectus voluptatum!"
            },
            ]);
            return {posts}
    }
}
</script>

<style>

</style>