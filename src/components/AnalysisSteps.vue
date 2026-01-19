<template>
    <span style="color: blue">{{props.node?.content?? "无数据"}}</span>
</template>
<script setup>
    const props = defineProps({ 
        node: { type: Object, required: false }
    })
     // 无法触发组件
    debugger;
</script>