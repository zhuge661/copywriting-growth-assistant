# Soul Writer

Soul Writer is a creator-focused script-writing skill for short-form video.

It is not a one-click copywriting template. It helps an AI agent first understand the creator, verify facts, work through the core idea with the creator, confirm the central claim, and then turn that thinking into a spoken script and platform-ready assets.

Chinese name: `灵魂写手`

Technical ID: `soul-writer`

## What It Helps With

- Short-form video scripts for Douyin, WeChat Channels, Xiaohongshu, TikTok, Reels, Shorts, LinkedIn, and X
- Chinese scripts, English scripts, and bilingual scripts
- English analysis and English script adaptation
- Cover text, video titles, hashtags, captions, and Xiaohongshu notes
- Topic digestion, creator positioning, and content angle development
- Creator-specific voice isolation across different personal brands
- Sample-based style learning and archive cleanup

## Core Idea

Great creator writing is not just wording. It is the creator's judgment, rhythm, worldview, and emotional temperature.

Soul Writer is designed around one rule:

> Define the person before writing the copy.

Before drafting, the skill reads `references/creator-profile.md` and, when relevant, only loads the active creator's dedicated profile. It avoids mixing one creator's tone, hooks, slogans, samples, and content lanes into another creator's work.

## Bilingual Analysis By Default

Soul Writer now treats bilingual output as the default. Unless the creator explicitly asks for Chinese-only or English-only, all analysis should include Chinese + English:

- facts;
- possible angles;
- risks;
- core claim;
- hooks;
- titles;
- packages;
- captions.

Soul Writer does not treat English output as a direct translation of Chinese copy.

For English or bilingual work, it rebuilds the idea for an English-speaking audience:

- What is the core claim?
- Why would an English-speaking audience care?
- What tension, misconception, or benefit should the hook attack?
- Which Chinese idioms, platform assumptions, or cultural shortcuts should not be translated literally?
- How can technical concepts become natural spoken English?
- Which format fits TikTok, Reels, Shorts, LinkedIn, or X?

Default bilingual format:

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

## English Analysis Output

When asked for analysis, `English analysis`, `English version`, `bilingual`, or content for an overseas audience, the skill should produce bilingual sections by default:

1. **Core Claim**: the central idea in one sentence.
2. **Audience Tension**: why the audience should care.
3. **Hook Options**: three hooks, usually contrarian, practical, and emotional.
4. **Plain-English Translation**: technical ideas rewritten as natural spoken English.
5. **Risk Notes**: facts to verify, phrases not to translate literally, and claims that may sound exaggerated or culturally off.

## Workflow

1. **Creator Profile**
   Read `references/creator-profile.md`.

2. **Fact Check**
   For AI products, models, versions, data, or time-sensitive topics, verify before writing.

3. **Digest The Topic**
   Help the creator sharpen their own point of view instead of forcing a template.

4. **Confirm The Core**
   Do not draft until the central claim is clear.

5. **Write**
   Generate the script, titles, hashtags, captions, and optional bilingual bridge.

6. **Self-Check**
   Check for creator voice, platform fit, factual risk, translation stiffness, and unwanted IP contamination.

## Files

```text
soul-writer/
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
        └── optional dedicated creator profiles
```

## Bilingual File Map

| Chinese file | English file |
| --- | --- |
| `SKILL.md` | `SKILL_EN.md` |
| `README.md` | `README_EN.md` |
| `references/creator-profile.md` | `references/creator-profile.en.md` |
| `references/samples-log.md` | `references/samples-log.en.md` |
| `references/archive/samples-archive.md` | `references/archive/samples-archive.en.md` |
| `agents/openai.yaml` | `agents/openai.en.yaml` |
| `LICENSE` | `LICENSE_CN.md` for Chinese reference only. The English MIT license is authoritative. |

## License

MIT License. See `LICENSE`.
