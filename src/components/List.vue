<!-- HTML -->
<template>
    <div class="view">
        <h1 class="title">{{title}}</h1>

        <ul>
            <!-- 使用v-for循环渲染事项 -->
            <!-- 使用v-bind判断是否完成事项 -->
            <li v-for="item in items" v-bind:class="{finish: item.isFinished}">
                {{item.text}}
            </li>
        </ul>
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
                items: [
                    {
                       text: "使用Vue开发项目",
                       isFinished: false
                    },
                    {
                       text: "阅读Vue文档",
                       isFinished: true
                    },
                ],
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

    .view .title{
        border-bottom: 1px solid gray;
    }

    .view ul li{
        margin: 10px 0;
        list-style: none;
    }

    .view .finish{
        color: grey;
        text-decoration: line-through;
    }
</style>