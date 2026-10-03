# 插画分层与复用（Illustration Layer Reuse）

**首版：v0.1.0**

一个用于 Photoshop 插画分层与素材复用的 Codex Skill。它帮助把合并插画按前后遮挡拆层，在保留原构图和可见像素的基础上，分离人物、装饰与前中后景；需要补出遮挡内容时，用局部 AI 生成，并将推测区域与原始像素区分开。

它特别强调两项独立验收：整幅合成能否还原原图，以及拆出的素材能否单独干净复用。这样可避免把“合成看起来正确”误当成“每个对象都已抠干净”。

## 使用

在 Codex 对话中附上插画，然后调用：

> 用 `$illustration-layer-reuse` 处理这张插画，保持原构图，按遮挡关系分层，AI 只补缺口。交付 PSD 和独立素材，并分别验收合成还原与素材复用。

续接已有项目时，提供输出目录，并要求先读取 `progress.md` 与 `manifest.json`，只处理未通过项目。

## 文件

- `illustration-layer-reuse/SKILL.md`：精简入口与执行顺序。
- `illustration-layer-reuse/references/quality.md`：局部 AI 补全与双重验收。
- `illustration-layer-reuse/references/photoshop.md`：Photoshop 自动化的身份、蒙版、坐标与保存检查。
- `illustration-layer-reuse/references/postmortem.md`：从真实分层任务中整理的问题与防止重演方式。
- `使用说明与短指令.md`：可复制的简短调用词。

## 边界

合并图无法证明遮挡后的原始细节和半透明物 alpha。此类内容需要标记为推测；AI 放大也不会增加原生图像细节。技能不承诺自动化能还原作者从未提供的图层。
