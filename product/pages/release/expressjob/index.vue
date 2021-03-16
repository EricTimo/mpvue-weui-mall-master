<!--  -->
<template>
<div>发布招工
    <div class="weui-panel my-panel">
        <div>
            <div>工种</div>
            <div>请选择工种</div>
            <div>项目所在地<span>（点击可添加/修改详细工程地址）</span></div>
            <div>-- --</div>
            <div>电话</div>
            <div>-- --</div>
            <div>联系人</div>
            <div>-- --</div>
            <div>用工要求<span>（点击模板即可选中）</span></div>
            <div>选择模板后，就能对该模板进行修改</div>
            <div>
                <textarea name="template1" id="t1" cols="30" rows="10">
                模板—∶ 深圳市招水电工师傅2名，260-350元/天，每个月 15号准时发生活费，包吃住，常年活动，非诚勿 扰，有意者电话联系我。
            </textarea>
                <textarea name="template2" id="t2" cols="30" rows="10">
                模板二∶ 深圳市招水电工师傅2名，要求∶有责任心，踏实肯干，260-350元/天，有意向者电话联系我。具体面谈，可报销来回火车票。
            </textarea>
                <textarea name="template3" id="t3" cols="30" rows="10">
                模板三∶ 深圳市招水电工大工2名，长期临时都行，服从安排。260-350元/天，非诚勿扰。
            </textarea>
            </div>
        </div>
        <mp-button class="submit">确认发布</mp-button>
    </div>
</div>
</template>

<script>
export default {
    name: "",
    data() {
        return {

        }
    },
    //生命周期 - 创建完成（访问当前this实例）
    created() {

    },
    //生命周期 - 挂载完成（访问DOM元素）
    mounted() {

    }
}
</script>

<style scoped>
/* @import url(); 引入css类 */
.my-panel {}
</style>
