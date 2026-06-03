# 灵魂写手 / Soul Writer

[English README](README_EN.md) · [English Skill Spec](SKILL_EN.md)

一个面向个人 IP 的短视频文案协作 Skill。它不是“一键出稿机”，而是让 AI 先确认使用人配置、查证事实、陪你消化选题、确认内核，再落成口播稿和平台配套。

当前 Skill 名称：`灵魂写手 / Soul Writer`

技术 ID：`soul-writer`

当前仓库目录：`wenan-chengzhang-zhushou-v5`

## 适合做什么

- 抖音、视频号、小红书口播文案
- 封面标题、视频标题、关键词、小红书笔记
- 英文解析、英文口播改写、双语短视频配套
- 热点选题消化
- 个人 IP 方法论表达
- 课程或产品轻推广文案
- 多次协作后的风格沉淀和样本复盘

## 英文版入口

如果你要给海外用户看，直接打开：

```text
README_EN.md
```

这个 skill 已支持 English analysis、English script、bilingual short-video package。更重要的是：**默认所有解析输出中英双语**，包括事实、角度、内核、钩子、风险、标题、配套。英文部分不是逐句翻译中文版，而是按英文受众和英文短视频语感重建表达。

本仓库已经补齐中英文两套开源说明：

| 中文文件 | 英文文件 |
| --- | --- |
| `SKILL.md` | `SKILL_EN.md` |
| `README.md` | `README_EN.md` |
| `references/creator-profile.md` | `references/creator-profile.en.md` |
| `references/samples-log.md` | `references/samples-log.en.md` |
| `references/archive/samples-archive.md` | `references/archive/samples-archive.en.md` |
| `agents/openai.yaml` | `agents/openai.en.yaml` |
| `LICENSE` | `LICENSE_CN.md`（中文参考译文，英文 MIT 原文为准） |

## 核心设计

### 1. 使用人配置

开始写之前，先在 `references/creator-profile.md` 里定义当前使用人：

- IP 名和账号名
- 一句话定位
- 核心受众
- 默认平台
- 话题轨道
- 固定口播结尾
- 品牌标签
- 强禁忌

如果换成另一个 IP 使用，必须先填写新的使用人配置，不能直接套用默认配置。

### 2. 跨 IP 隔离

v5 重点解决“心智污染”问题：不同 IP 的表达习惯、样本、固定标语和话题轨道不能互相污染。

开源版本不内置任何默认使用人的专属规则。若你要给某个 IP 使用，应新建自己的 profile，例如：

```text
references/profiles/your-creator.md
```

只有当前使用人明确匹配该 profile 时才读取它。换成其他 IP 时，应创建新的 profile 和样本库。

### 3. 三种工作模式

- **完整协作模式**：适合高信息密度选题。先查证，再多轮消化，确认内核后落稿。
- **半快出模式**：AI 查证后给 3 个内核候选，使用人拍板后落稿。
- **快出模式**：适合低信息密度或赶量内容，直接按配置和规则落稿。

### 4. 英文 / 双语扩展

v5 现在默认支持中英双语解析和英文成稿。它不会把中文稿逐句翻译成英文，而是先重建：

- 英文受众为什么在意；
- 英文短视频应该怎么开头；
- 哪些中文梗不能直译；
- 专业概念如何变成自然 spoken English；
- 英文标题、封面、hashtags、caption 怎么适配 TikTok / Shorts / Reels / LinkedIn。

默认双语解析格式：

```markdown
## 中文
- 事实：
- 可打角度：
- 风险点：
- 内核：
- 钩子：

## English
- Facts:
- Possible Angles:
- Risk Notes:
- Core Claim:
- Hooks:
```

### 5. 样本库新陈代谢

为避免 `samples-log.md` 越写越长，v5 加入归档瘦身机制：

- 活跃样本库只保留最近 10 条完整样本。
- 旧样本归档到 `references/archive/samples-archive.md`。
- 每 10 条沉淀一次阶段摘要。
- 默认写作只读取当前配置、已固化规则、阶段摘要和最近 5 条样本。

## 目录结构

```text
wenan-chengzhang-zhushou-v5/
├── SKILL.md
├── SKILL_EN.md
├── README.md
├── README_EN.md
├── LICENSE
├── LICENSE_CN.md
├── agents/
│   ├── openai.yaml
│   └── openai.en.yaml
└── references/
    ├── creator-profile.md
    ├── creator-profile.en.md
    ├── samples-log.md
    ├── samples-log.en.md
    ├── archive/
    │   ├── samples-archive.md
    │   └── samples-archive.en.md
    └── profiles/
        └── （放置你自己的专属 profile，可选）
```

## 使用方式

把整个文件夹放到 Codex / OpenAI Agents 的 skills 目录中，或在支持 Skill 的环境中引用这个文件夹。

启动时让 AI 先读：

```text
SKILL.md
references/creator-profile.md
references/samples-log.md
```

如果当前使用人有专属 profile，再读取对应文件，例如：

```text
references/profiles/your-creator.md
```

## 开源注意

开源版本不包含任何个人 IP 的默认 profile 或私有样本。使用时请创建自己的 profile 和样本库，避免把一个账号的表达习惯带到另一个账号里。

## License

MIT License. See `LICENSE`.
