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

    const props = defineProps({
        content: { type: String, required: true }
    });

    const customId = `mdContainer`;

    const CustomHtmlTags = ["TaskPlan", "AnalysisSteps"];

    const content =  `
    <hide>uid:b238ea9cb1a44ae489247aed335a0248</hide>

    <TaskPlan>
    已收到您关于xxx的组织机构画像的任务请求，我将按照以下步骤执行该任务：                            
    - 匹配并确认目标组织机构
    - 构建组织机构画像管理数据
    </TaskPlan>


    <AnalysisSteps>
    # 匹配信息和确认组织机构
    ## 深度思考
    - 
    - 好的，我现在需要处理用户的输入：“生成x的织机构画像”。首先，我需要确定用户是否提到了组织机构的名称。用户提到的“x”看起来像是一个公司名称，但可能存在拼写错误，比如“织机构”应该是“组织机构”。不过，这里的关键是提取组织机构名称。根据规则，我需要检查用户输入中的组织名称，并去除所有后缀，比如“集团、公司、股份有限公司”等。但“x”这个名称中没有明显的后缀，比如“公司”或“集团”之类的词。不过，可能用户输入有误，比如“织机构”可能是“组织机构”的笔误，但这里的问题是关于提取组织名称。接下来，我需要确认“x”是否是一个有效的组织机构名称。x是印度的一家电信公司，全称可能是x，但用户输入中没有提到“Limited”或类似的后缀。因此，根据规则，如果名称中没有后缀，就保留原始名称。所以，这里应该提取“x”作为品牌名称。另外，需要检查是否有地域或业务修饰词。例如，如果名称中有“（深圳）”或“科技”之类的词，需要保留业务关键词，但这里没有。因此，直接保留“x”。还要确保没有其他可能的后缀被遗漏。例如，如果用户输入的是“x”，那么需要去掉“公司”得到“x”。但当前输入中没有这样的后缀，所以直接保留。最后，检查是否符合返回“unknow”的条件。用户输入中包含了一个可能的组织名称，且去除后缀后是有效的品牌名称，因此不应返回“unknow”。
    ## 多维度匹配组织机构管理数据
    - 调用数据接口，机构画像关联数据匹配中......
    - 该机构没有关联数据匹配。
    </AnalysisSteps>
    &#10006; 该机构没有关联机构数据匹配，无法进行机构画像生成。
    `
    setCustomComponents(customId, {
        TaskPlan: AnalysisPlan,
        AnalysisSteps
    });
</script>