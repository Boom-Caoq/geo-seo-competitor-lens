# 竞对透视 · GEO×SEO

> Open-source Cursor / Agent Skill：输入一个网址，自动找竞对、对比 SEO 外链与各 AI 模型引用来源（GEO），打分并给出 30/90 天可执行优化方案。

**Repo:** https://github.com/Boom-Caoq/geo-seo-competitor-lens  
**Skill id:** `geo-seo`  
**License:** MIT

---

## 它能做什么

| 能力 | 说明 |
| --- | --- |
| 识别竞对 | 根据站点自述 + SERP + 同类产品，锁定 3–5 个主竞对 |
| SEO 外链透视 | 外链域名类型、锚文本/落地页倾向、可获链内容资产、技术可见性 |
| GEO / AI 引用 | 对同一组核心问题，记录各模型是否提及你/竞对、实际引用域名 |
| 评分卡 | 内容可引用性 / 外链 / 技术 / 关键词 / GEO，0–100 可对比 |
| 优化清单 | 白帽向 30 天 + 90 天动作，含优先级与验收标准 |

**不做：** 编造外链/引用、黑帽买卖链接、假装已接入 Ahrefs/Semrush。

---

## 快速开始（Cursor / 兼容 Agent）

### 方式 A：复制文件夹

1. 下载本仓库，或只取 [`skills/geo-seo/`](./skills/geo-seo/)
2. 把整个 `geo-seo` 文件夹放进你的 Skills / workflows 目录（需含 `SKILL.md`）
3. 新开对话，对 Agent 说：

```text
用「竞对透视 · GEO×SEO」分析 https://example.com
行业：SaaS，语言：中英文，对标 5 个竞对
```

### 方式 B：Agent 上传 Skill

部分产品支持「上传含 `SKILL.md` 的文件夹」（常见限制：单文件 ≤10MB，总包 ≤30MB）。直接上传 `skills/geo-seo/` 即可。

### 方式 C：本机 zip

```bash
cd skills && zip -r ../geo-seo-skill.zip geo-seo
```

把 `geo-seo-skill.zip` 解压到 Skills 目录后同上调用。

---

## 输入 / 输出

**输入**
- 必填：目标网址
- 可选：行业关键词、国家/语言、对标数量（默认 3–5）

**输出结构（固定）**
1. 一句话总评 + 总分  
2. 竞对表  
3. SEO 外链来源对比  
4. 分模型 AI 引用来源表  
5. 评分卡（含子分与依据）  
6. 30/90 天优化清单  
7. 数据缺口说明（无付费工具或模型不可访问时）

完整执行规则见 [`skills/geo-seo/SKILL.md`](./skills/geo-seo/SKILL.md)。

---

## 功能说明（流程）

1. **边界**：补全 `https://`；查不到的标「未验证」；只给白帽建议。  
2. **找竞对**：首页语义 + 搜索引擎 + 相似产品，筛出主竞对。  
3. **SEO**：反链概况、锚文本、内容资产、sitemap/robots/hreflang 等公开信号。  
4. **GEO**：对品牌词 / 品类词 / 对比词 /「最佳·怎么选」等问题，探测 Perplexity、Copilot、AI Overview 等带引用渠道。  
5. **打分对比**：五维评分 + 「最大被拉开口子」与「可加码优势」。  
6. **落地清单**：内容 / 外链 / 技术 / GEO，每条含动作、影响维度、P0–P2、验收标准。

---

## 仓库结构

```text
geo-seo-competitor-lens/
├── README.md                 # 本说明
├── LICENSE                   # MIT
├── docs/
│   ├── usage.md              # 详细使用教程
│   └── features.md           # 功能性说明
└── skills/
    └── geo-seo/
        └── SKILL.md          # Skill 源码（Agent 执行规范）
```

---

## 适用 / 不适用

- ✅ 独立站、SaaS、内容站、出海工具站  
- ✅ 想搞清「谁在喂养模型」与外链差距的运营 / 增长  
- ❌ 想买垃圾外链、刷引用量

---

## 贡献

Issue / PR 欢迎。改 Skill 行为请直接改 `skills/geo-seo/SKILL.md`，并同步更新 `docs/`。

---

## 致谢

开源分享给做 SEO / GEO 的独立站与 Agent 用户。Star 与反馈都有帮助。
