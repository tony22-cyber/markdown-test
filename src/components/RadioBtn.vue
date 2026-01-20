<template>
    <span style="color: green">{{props.node?.content?? "无数据"}}</span>
</template>
<script setup>
    const props = defineProps({ 
        node: { type: Object, required: false }
    })
     // 无法获取节点内容且raw的结束标识错误，如：（raw:<RadioBtn></radiobtn>）
    debugger;
</script>
