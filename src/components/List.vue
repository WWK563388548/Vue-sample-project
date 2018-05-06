<!-- HTML -->
<template>
    <div class="view">
        <h1 class="title">{{title}}</h1>
        <!-- 按下回车键时@keyup.enter生效，并执行方法addNewData -->
        <!-- 使用v-model来进行双向绑定 -->
        <input v-model="newData" @keyup.enter="addNewData" />
        <ul>
            <!-- 使用v-for循环渲染事项 -->
            <!-- 使用v-bind判断是否完成事项 -->
            <!-- 使用@click来绑定click事件（或其他事件） -->
            <li v-for="item in items" v-bind:class="{finish: item.isFinished}" @click="toggleFinish(item)">
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
                items: [],
                newData: '',
            }
        },
        methods: {
            toggleFinish: function(item){
                // 改变isFinished状态
                item.isFinished = !item.isFinished;
            },
            addNewData: function(){
                // console.log(this.newData);
                this.items.push(
                    {
                       text: this.newData,
                       isFinished: false
                    },
                );
                // 将输入框中的输入传递给父组件App.vue
                // 自定义事件(myInput为事件名, this.newData为想要传送的参数，即input输入的内容)
                // 触发myInput事件，并且传递参数
                this.$emit('myInput', this.newData);

                // 当输入框为空时,点回车直接清空输入框内容
                this.newData = '';
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