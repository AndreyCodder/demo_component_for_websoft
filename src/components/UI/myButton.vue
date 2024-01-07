<template lang="">
    <button>
        <slot></slot>
    </button>
</template>
<script>
export default {
    
}
</script>
<style scoped>
    button{
        padding: 10px;
        border: 1px solid indigo;
        cursor: pointer;
        background-color: transparent;
    }
</style>