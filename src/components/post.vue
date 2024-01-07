<template lang="">
    <div class="post">
        <div>
            <div class="postTitle">
                {{ post.title }}
            </div>
            <div class="postBody">
                {{ post.body }}
            </div>
            <div class="likesText">
                likes: {{ post.likes }}
            </div>
            <button class="butt like" @click="like(post.id)">+</button>
            <button class="butt dislike" @click="dislike(post.id)">-</button>
        </div>
        <div style="align-self: flex-end;">
            <myButton class="deleteButton" @click="deletePost(post.id)">Delete</myButton>
        </div>
    </div>
</template>
<script>
import myButton from './UI/myButton.vue';
export default {
    components:{
        myButton
    },
    props:{
        post:{
            type: Object,
            required: true,
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
    .post{
        padding: 15px;
        border: 2px solid indigo;
        border-radius: 5px;
        margin: 10px 20px;
        display: flex;
        justify-content: space-between;
    }
    .butt{
        padding: 5px;
        background-color: transparent;
        border: 1px solid indigo;
        border-radius: 50%;
        margin-right: 10px;
        width: 28px;
        height: 28px;
    }
    .butt:hover{
        background-color: indigo;
        box-shadow: 1px 1px 10px 1px rgba(0, 0, 0, 0.514);
        cursor: pointer;
    }
    .postTitle{
        font-size: 20px;
        padding: 10px;
        font-weight: 600;
    }
    .postBody{
        font-size: 18px;
        padding: 10px;
    }
    .deleteButton{
        align-self: flex-end;
    }
</style>