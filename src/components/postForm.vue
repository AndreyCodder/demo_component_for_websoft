<template lang="">
    <form @submit.prevent>
        <input 
            type="text" 
            name="title" 
            id="title" 
            placeholder="Название поста" 
            v-model="post.title" 
        >
        <input 
            type="text" 
            name="body" 
            id="body" 
            placeholder="Текст поста" 
            v-model="post.body" 
        >
        <myButton class="createButton" @click="createPost">Создать пост</myButton>
    </form>
</template>
<script>

import myButton from './UI/myButton.vue';
export default {
    components:{
        myButton
    },
    data() {
        return {
            post: {
                title: "",
                body: ""
            }
        }
    },
    methods: {
        createPost(){
            this.post.id = Date.now();
            this.post.likes = 0;
            this.$emit("create", this.post);
            this.post = {
                title: "",
                body: ""
            }
        }
    },
}
</script>
<style scoped>
    form{
        display: flex;
        flex-direction: column;
        padding: 20px;
        
    }
    input{
        background-color: transparent;
        border: 1px solid indigo;
        font-size: 16px;
        padding: 10px;
        margin: 15px 0;
    }
    .createButton{
        align-self: flex-end;
    }
</style>