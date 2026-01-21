<template>
    <span style="color: green">{{props.node?.content?? "无数据"}}</span>
</template>
<script setup>
    const props = defineProps({ 
        node: { type: Object, required: false }
    })
    debugger;
</script>
