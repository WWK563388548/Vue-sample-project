<template>
    <div class="headerview">
        <h1>{{msg}}</h1>
    </div>
</template>

<script>
    export default{
        data(){
            return{
                title: "标题部分..."
            }
        }, // 父向子传参第一步：添加props
        props: {
            msg:{ // 这里可以看作是自定义标签属性
                // 设置传输数据类型
                type: String,
                default: "默认值"

            }
        }
    }
</script>

<style>
</style>