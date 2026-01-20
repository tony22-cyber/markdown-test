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

    const content =  `
<hide>uid:6421ed2c189341e08eae49375bc1032f</hide>

<TaskPlan>
已收到您关于刻画xx组织机构画像的任务请求，我将按照以下步骤执行该任务：                            
- 匹配并确认目标组织机构
- 构建组织机构画像管理数据
</TaskPlan>

<AnalysisSteps>
# 匹配信息和确认组织机构
## 深度思考
- 好的，我现在需要处理用户的输入“刻画xx组织机构画像”，根据规则提取组织机构名称。首先，用户提到的是“xx组织机构”..
## 组织机构查询关键字:XX
</AnalysisSteps>

<RadioBtn>
<title>组织结构列表</title>
<content>少时诵诗书</content>
</RadioBtn>

<hide>库中没有该目标相关数据，无法生成机构画像。</hide>
    `
    setCustomComponents(customId, {
        taskplan: AnalysisPlan,
        analysissteps: AnalysisSteps,
        radiobtn: RadioBtn
    });
</script>
