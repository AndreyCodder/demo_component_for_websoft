<template lang="">
    <postForm 
        @create="createPost"
    />
    <postList 
        :posts="posts"
        @like="like"
        @dislike="dislike"
        @deletePost="deletePost"
    />
    
</template>
<script>
import postForm from "./components/postForm"
import postList from "./components/postList.vue";
export default {
    components: {
        postForm, postList
    },
    data() {
        return {
        post_title: "",
        posts: [
            {
                id: 1,
                title: "Post title 1",
                body: "Post body about all in the world",
                likes: 0
            },
            {
                id: 2,
                title: "Post title 2",
                body: "Post body about all in the world 2",
                likes: 0
            },
            {
                id: 3,
                title: "Post title 3",
                body: "Post body about all in the world 3",
                likes: 0
            },
            {
                id: 4,
                title: "Post title 4",
                body: "Post body about all in the world 4",
                likes: 0
            },
        ]
        };
    },
    methods: {
        like(postId){
            this.posts.find(post => post.id == postId).likes++
        },
        dislike(postId){
            this.posts.find(post => post.id == postId).likes--
        },
        deletePost(postId){
            this.posts = this.posts.filter(post => post.id != postId)
        },
        createPost(post){
            this.posts.push(post)
        }
    },
};
</script>
<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    
</style>
