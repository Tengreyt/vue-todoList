<template>
    <div class="app">
        <post-form  
        @create="createPost"/>
        <post-list :posts="posts"/>
    </div>
</template>

<script>

import PostForm from './components/PostForm.vue'
import PostList from './components/PostList.vue'
export default {
    components : {
        PostForm, PostList
    },
    data() {
        return {
            posts: [
                {id:1, title: ' Javascrips 1', body: ' Описания поста 1'},
                {id:2, title: ' Javascrips 2', body: ' Описания поста 2'},
                {id:3, title: ' Javascrips 3', body: ' Описания поста 3'},
                {id:4, title: ' Javascrips 4', body: ' Описания поста 4'},
            ],
           
        }
    },
    methods: {
        createPost(post) {
           this.posts.push(post)
        },
        
    }
}

</script>

<style scoped>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.app {
    padding: 20px
}

</style>
