<template>
    <MarkdownRender
        :custom-id="customId"
        :content="content"
        :custom-html-tags="CustomHtmlTags"
    />
</template>
<script setup>
    import MarkdownRender, { setCustomComponents } from "markstream-vue";
    import AnalysisPlan from "./AnalysisPlan.vue";
    import AnalysisSteps from "./AnalysisSteps.vue";
    import RadioBtn from "./RadioBtn.vue";

    const props = defineProps({
        content: { type: String, required: true }
    });

    const customId = `mdContainer`;

    const CustomHtmlTags = ["TaskPlan", "AnalysisSteps", "RadioBtn"];

// 错误示例
const content =  `
<TaskPlan>
已收到您关于刻画xx组织机构画像的任务请求，我将按照以下步骤执行该任务：                            
- 匹配并确认目标组织机构
- 构建组织机构画像管理数据
</TaskPlan>
测试案例
<RadioBtn>
<title>组织结构列表</title>
<content>少时诵诗书</content>
</RadioBtn>
`
// 正常示例
const case1 =  `
<TaskPlan>
已收到您关于刻画xx组织机构画像的任务请求，我将按照以下步骤执行该任务：                            
- 匹配并确认目标组织机构
- 构建组织机构画像管理数据
</TaskPlan>
测试案例
<RadioBtn>
    <title>组织结构列表</title>
    <content>少时诵诗书</content>
</RadioBtn>
`
// 正常示例
const case2 =  `
<TaskPlan>
已收到您关于刻画xx组织机构画像的任务请求，我将按照以下步骤执行该任务：                            
- 匹配并确认目标组织机构
- 构建组织机构画像管理数据
</TaskPlan>
<RadioBtn>
<title>组织结构列表</title>
<content>少时诵诗书</content>
</RadioBtn>
`

    setCustomComponents(customId, {
        taskplan: AnalysisPlan,
        analysissteps: AnalysisSteps,
        radiobtn: RadioBtn
    });
</script>
