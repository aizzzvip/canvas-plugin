---
name: canvas
description: 操作无限画布当前网页画布，读取节点、选区、创建文本节点、创建生成流程、连接节点或触发生成。
---

# 无限画布

你正在帮助用户操作无限画布（https://img.aizzz.vip）网页画布。需要理解或改动画布时，优先使用已配置的 `infinite-canvas` MCP 工具；不要让用户手动复制 JSON、URL 或 token。向用户提到本站时统一称为「无限画布」。

## 工作流

- 如果用户还没有打开或连接网页画布，使用 `open-canvas` 技能打开无限画布，不要要求用户手动复制 URL 或 token。
- 操作前先用 `canvas_get_state` 读取当前画布；如果用户明确提到选中内容、当前节点或“这个”，先用 `canvas_get_selection`。
- 创建单个文本内容优先用 `canvas_create_text_node`。
- 创建生成内容优先用 `canvas_generate_text`、`canvas_generate_image`、`canvas_generate_video`、`canvas_generate_audio`。
- 需要把提示词、配置和生成节点串成流程时，使用 `canvas_create_generation_flow` 或项目已有的流程工具。
- 需要批量增删改、移动、连接节点或设置视口时，使用 `canvas_apply_ops`。
- 生成图片、视频使用的是用户在无限画布里配置的渠道和模型；需要指定模型时，先用 `workbench_image_get_config` 或 `workbench_video_get_config` 查看可选模型，不要编造模型名。
- 不要模拟鼠标点击，不要要求用户手动复制 JSON。
- 写入画布的操作会由网页侧边栏做二次确认，按当前工具结果继续推进即可。

## 风格

- 页面文案和画布节点内容默认使用中文。
- 生成节点、配置节点和提示词节点要保持结构清晰，方便用户继续编辑。
- 批量创建节点时注意给节点留出间距，不要堆叠在同一个位置。
- 图片、视频、音频等媒体节点默认保留原始比例；只有用户明确要求自由变形时才改变比例。
- 生成流程尽量少而清楚，优先让用户一眼能看懂节点关系。
