<template>
    <div class="person">
        <h2>姓名：{{ person.name }}</h2>
        <h2>年龄：{{ person.age }}</h2>
        <h2 ref="title">哈哈哈</h2>
        <button @click="showTitle">修改标题</button>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>

    </div>
</template>
<script lang="ts" setup name="Person">
import { ref, watch } from 'vue'
let title = ref()


function showTitle() {
    console.log(title.value)
    title.value.innerText = "nnnn";
}
let person = ref({
    name: "zhangsan",
    age: 28
})
function changeName() {
    person.value.name = "lisi";
}
function changeAge() {
    person.value.age += 1;
}
watch(person, (newValue, oldValue) => {
    console.log(newValue, oldValue);
}, { deep: true });

</script>
<style scoped>
.app {
    background-color: #fff;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
}
</style>
