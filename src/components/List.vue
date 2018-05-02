<!-- HTML -->
<template>
    <div class="view">
        <h1>{{title}}</h1>
    </div>
</template>

<!-- JS -->
<script>
    // new Vue()
    export default{
        name: "List",
        // ES6写法
        data(){
            return {
                title: "我的待办事项",
            }
        }
    }
</script>

<!-- CSS -->
<style>
    .view{
        width: 400px;
        border: 1px solid gray;
        margin: 20px auto;
    }
</style>