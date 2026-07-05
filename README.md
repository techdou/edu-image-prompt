# Edu Image Prompt 🎨

> 把任何知识点变成**可直接粘贴使用的 AI 生图 Prompt** — 专为教育场景优化，中文渲染可靠。

[![Skill](https://img.shields.io/badge/AI%20Agent-Skill-blue)]()
[![Models](https://img.shields.io/badge/Supports-GPT%20Image%202%20%7C%20Nano%20Banana%20%7C%20MJ%20v7-green)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow)](./LICENSE)

## 它解决什么问题？

教育内容创作者（老师、科普博主、课程设计师）经常需要为知识点配图。直接让 AI "画一张关于 X 的图"会得到漂亮但空洞的营销海报——文字乱码、信息缺失、没有教学价值。

这个 skill 的核心价值：**把知识点转化为结构化的 5-block 生图 prompt**，让 AI 生成真正有教学意义、文字准确、布局清晰的配图。

## 核心方法：5-Block 结构化 Prompt

每个 prompt 都遵循这个经过 300+ 次生成验证的结构：

```
[1] CANVAS    — 尺寸、背景、主色调（先定画布再定内容）
[2] HEADER    — 精确标题文本（引号包裹确保渲染准确）
[3] BLOCKS    — 5-8 个教学内容模块
[4] VISUAL    — 线条/图标/箭头/风格
[5] CONSTRAINTS — 文本准确性约束 + 禁止项
```

**关键技巧**：每个中文字符串都用 `THE TEXT READS: "..."` 引号包裹 — 这是中文渲染准确性的最大杠杆（来自 OpenAI cookbook）。

## 快速开始

```
用户：把 RAG 讲给家长听，用生活类比
       ↓
Skill 执行 4 步 SOP：
  Step 1: 问询风格选择（领域/质感/平台/模型）
  Step 2: 知识点拆解为 3-4 个可绘制的视觉目标 ← 关键步骤
  Step 3: 用 5-block 模板组装 prompt
  Step 4: 质量验证 → 输出
       ↓
输出：可直接粘贴到 GPT Image 2 / Nano Banana 的 prompt
```

## 4 步工作流

| 步骤 | 做什么 | 为什么重要 |
|------|--------|-----------|
| **Step 1 问询** | 选择领域美学、渲染介质、展示平台、目标模型 | 确保风格匹配场景 |
| **Step 2 拆解** | 把知识点分解为 3-4 个**可绘制**的视觉目标 | 防止直接跳到 prompt 的 #1 错误 |
| **Step 3 生成** | 用 5-block 模板组装结构化 prompt | 确保布局/文本/约束完整 |
| **Step 4 验证** | 运行质量检查清单 | 确保输出可直接使用 |

## 支持的模型

| 模型 | 中文渲染 | 最佳场景 |
|------|---------|---------|
| **GPT Image 2** | ✅ 最佳 | 教育卡片、信息图（默认推荐） |
| **Nano Banana** | ✅ 良好 | 快速批量生成系列卡片 |
| **Midjourney v7** | ⚠️ 避免 CJK | 艺术插画、无文字背景图 |

## 12 种内容模块

从模块池中选 5-8 个组装成卡片：

`定义` · `例子` · `步骤` · `对比` · `误区` · `类比` · `金句` · `评分` · `流程箭头` · `局部放大` · `警告` · `记忆口诀`

## 文档索引

| 文档 | 内容 |
|------|------|
| [`SKILL.md`](./SKILL.md) | Agent 技能定义、4 步 SOP |
| [`references/prompt-rules.md`](./references/prompt-rules.md) | 5-block 模板 + 文本渲染技巧 |
| [`references/model-guide.md`](./references/model-guide.md) | GPT Image 2 / Nano Banana / MJ 适配 |
| [`references/type-guide.md`](./references/type-guide.md) | 8 种预设类型 + 12 模块池 |
| [`references/style-config.md`](./references/style-config.md) | 领域美学 + 调色板 |
| [`references/examples.md`](./references/examples.md) | 3 个完整示例 |
| [`references/output-format.md`](./references/output-format.md) | 输出格式规范 |
| [`references/validation.md`](./references/validation.md) | 质量验证清单 |
| [`references/troubleshooting.md`](./references/troubleshooting.md) | 6 种常见问题修复 |
| [`CHANGELOG.md`](./CHANGELOG.md) | 版本记录 |

## License

[MIT](./LICENSE)
