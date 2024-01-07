<template lang="">
    <post 
        v-for="post in posts"
        :post="post"
        @like="like"
        @dislike="dislike"
        @deletePost="deletePost"
    />
</template>
<script>
import post from '@/components/post'
export default {
    components:{
        post
    },  
    props:{
        posts: {
            type: Array,
            required: true
        }
    },
    methods:{
        like(postId){
            this.$emit('like', postId);
        },
        dislike(postId){
            this.$emit('dislike', postId);
        },
        deletePost(postId){
            this.$emit('deletePost', postId);
        }
    }
}
</script>
<style scoped>

</style>