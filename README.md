# AI Agent Skills

技能集合，涵盖浏览器自动化、内容创作、社交媒体发布、设计质量、Obsidian 笔记等多个领域。

---

## 技能目录

### 🌐 网络 & 内容采集

| 技能                       | 说明                                                                                                 |
| -------------------------- | ---------------------------------------------------------------------------------------------------- |
| `firecrawl`                | Firecrawl CLI，支持网页搜索、单页抓取、站点爬取、浏览器交互、AI 自主提取等，输出 LLM 友好的 Markdown |
| `defuddle`                 | 从网页提取干净 Markdown 内容，去除广告和导航噪音                                                     |
| `autocli`                  | 复用 Chrome 登录态把 55+ 网站变成 CLI，支持读取热榜、搜索、发帖、收发消息等站点交互                  |
| `baoyu-url-to-markdown`    | 通过 Chrome CDP 抓取任意 URL 并转为 Markdown，内置 X/Twitter、YouTube、Hacker News 等适配器          |
| `baoyu-youtube-transcript` | 下载 YouTube 视频字幕/封面图，支持多语言、翻译、章节和说话人识别                                     |

### 🖥️ 浏览器自动化

| 技能            | 说明                                                                        |
| --------------- | --------------------------------------------------------------------------- |
| `agent-browser` | AI 代理浏览器自动化 CLI，支持页面导航、表单填写、按钮点击、截图、数据提取等 |

### 🏞️ AI 图像生成

| 技能                        | 说明                                                                                                           |
| --------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `baoyu-cover-image`         | 文章封面图生成，5 维度定制（类型/配色/渲染/文字/氛围），支持多种宽高比                                         |
| `baoyu-article-illustrator` | 分析文章结构，识别配图位置，按类型×风格二维矩阵生成插图                                                        |
| `baoyu-comic`               | 知识漫画生成，支持清线/日漫/写实/水墨/粉笔等多种画风和基调                                                     |
| `baoyu-infographic`         | 专业信息图生成，21 种布局类型 × 20 种视觉风格                                                                  |
| `baoyu-xhs-images`          | 小红书图文系列生成，11 种视觉风格 × 8 种布局，优化社交平台传播                                                 |
| `baoyu-compress-image`      | 图片压缩为 WebP/PNG，自动选择最佳压缩工具                                                                      |
| `editorial-card-screenshot` | 高密度编辑式 HTML 信息卡片生成，瑞士国际风格排版，支持 8 种宽高比（3:4/4:3/1:1/16:9 等），输出 HTML + PNG 截图 |
| `canvas-design`             | 博物馆级视觉艺术设计，先创建设计哲学宣言，再在画布上以 .png/.pdf 输出，内置 80+ 字体                           |

### 📋 文档处理

| 技能             | 说明                                                                                           |
| ---------------- | ---------------------------------------------------------------------------------------------- |
| `minimax-docx`   | 专业 DOCX 文档创建、编辑和格式化，使用 OpenXML SDK，支持从零创建/填充编辑/模板格式化           |
| `minimax-xlsx`   | Excel 电子表格处理，支持创建、读取、分析、编辑和验证 .xlsx/.csv 文件，含公式计算和专业格式化   |
| `minimax-pdf`    | PDF 创建与生成，注重视觉质量和设计感，适用于报告、提案、简历等场景                             |
| `pptx-generator` | PowerPoint 演示文稿生成、编辑和读取，支持从零创建（封面/目录/内容/分隔/总结页）和编辑现有 PPTX |

### ✍️ 内容创作 & 翻译

| 技能                     | 说明                                                                                      |
| ------------------------ | ----------------------------------------------------------------------------------------- |
| `baoyu-translate`        | 三模式翻译：快速直译、常规（先分析再翻译）、精翻（分析→翻译→审校→润色），支持自定义术语表 |
| `baoyu-format-markdown`  | 格式化纯文本或 Markdown，添加标题、摘要、加粗、列表等，含 CJK 排版修正                    |
| `baoyu-markdown-to-html` | Markdown 转微信兼容的带主题样式 HTML，支持代码高亮、数学公式、PlantUML、脚注等            |
| `humanizer`              | 去除 AI 写作痕迹，检测并修复膨胀修辞、推广用语、破折号过度使用、AI 词汇等                 |

### 📱 社交媒体发布

| 技能                   | 说明                                                               |
| ---------------------- | ------------------------------------------------------------------ |
| `baoyu-post-to-wechat` | 发布内容到微信公众号，支持文章和图文模式，API 或浏览器两种方式     |
| `baoyu-post-to-weibo`  | 发布微博，支持文字、图片、视频和头条文章，通过真实 Chrome 绕过反爬 |
| `baoyu-post-to-x`      | 发布内容到 X/Twitter，支持普通推文（含图片/视频）和长文 Article    |

### 🎬 视频 & 演示

| 技能                      | 说明                                                                           |
| ------------------------- | ------------------------------------------------------------------------------ |
| `slidev`                  | 面向开发者的 Markdown 幻灯片演示工具，支持 Vue 组件、代码高亮、动画和交互      |
| `baoyu-slide-deck`        | 从内容生成专业幻灯片图片，支持 16+ 种风格预设，输出 PPTX/PDF                   |
| `guizang-ppt-skill`       | 生成电子杂志 × 电子墨水风格的单文件横向翻页网页 PPT，适合分享、演讲和发布会    |

### 🎨 前端设计 & UX

| 技能                          | 说明                                                                 |
| ----------------------------- | -------------------------------------------------------------------- |
| `impeccable`                  | 设计、重构、审查和打磨生产级前端界面，覆盖 UX、视觉层级、动效、可访问性和响应式体验 |
| `huashu-design`               | 用 HTML 做高保真原型、交互 Demo、幻灯片、动画和设计变体探索          |
| `vercel-react-best-practices` | React / Next.js 性能优化与工程实践指南，适合写、审、改前端代码时参考 |

### 🔎 SEO

| 技能                    | 说明                                                     |
| ----------------------- | -------------------------------------------------------- |
| `ai-seo`               | AI 搜索、AEO、GEO 与 LLM 引用可见性优化                  |
| `programmatic-seo`     | 使用模板和数据批量创建 SEO 页面                          |
| `seo`                  | 综合 SEO 分析、审计、技术与内容优化                       |
| `seo-ahrefs`             | Ahrefs 数据接入与 SEO 分析                                |
| `seo-audit`              | SEO 健康检查、技术 SEO、排名与索引问题诊断                |
| `seo-bing`               | Bing Webmaster Tools 数据接入                             |
| `seo-backlinks`        | 外链画像、毒链检测、竞品外链差距与链接建设分析             |
| `seo-cluster`          | SEO 主题集群与内容规划                                   |
| `seo-competitor-pages` | 竞品页面与竞品 SEO 分析                                  |
| `seo-content`          | SEO 内容分析、优化与创作                                 |
| `seo-dataforseo`       | 通过 DataForSEO 获取关键词、SERP 与 SEO 数据              |
| `seo-drift`            | SEO 内容与技术变更漂移监测                               |
| `seo-ecommerce`        | 电商 SEO、商品页与结构化数据优化                          |
| `seo-firecrawl`        | 使用 Firecrawl 抓取网页并进行 SEO 分析                    |
| `seo-flow`             | SEO 工作流编排与自动化                                   |
| `seo-geo`              | 面向 AI Overviews、ChatGPT、Perplexity 的 GEO 优化         |
| `seo-google`           | Google Search、Search Console 与 SEO 数据分析             |
| `seo-hreflang`         | 多语言、多地区网站的 hreflang 配置与审计                  |
| `seo-image-gen`        | 生成 OG 图、博客配图、产品图、信息图等 SEO 图片资产        |
| `seo-images`           | 图片 SEO、alt 文本、尺寸、格式与性能优化                  |
| `seo-local`            | 本地 SEO、Google Business Profile 与本地排名优化           |
| `seo-maps`             | 地图、本地商家与地理位置 SEO                              |
| `seo-page`             | 单页面 SEO 分析与优化                                    |
| `seo-performance`      | Core Web Vitals、Lighthouse 与性能审计                    |
| `seo-plan`             | SEO 策略、路线图与执行计划                                |
| `seo-profound`         | Profound AI 搜索与 GEO 数据接入                           |
| `seo-programmatic`     | 程序化 SEO 页面与规模化落地页建设                         |
| `seo-schema`           | Schema.org、JSON-LD 与结构化数据                         |
| `seo-seranking`        | SE Ranking 数据接入与排名分析                            |
| `seo-sitemap`          | XML sitemap 生成、分析与问题排查                          |
| `seo-sxo`              | 搜索体验优化（SXO）与转化导向的 SEO                       |
| `seo-technical`        | 技术 SEO、抓取、索引、性能与网站健康                      |
| `seo-unlighthouse`     | Unlighthouse 批量 Lighthouse 性能审计                     |
| `seo-visual`           | 截图、首屏与移动端视觉信号审计                            |
| `site-architecture`    | 网站层级、导航、URL 结构与内链规划                        |

### 📧 Google Workspace

| 技能  | 说明                                                                                                                                 |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `gog` | Google Workspace CLI，支持 Gmail 收发邮件、Calendar 日程管理、Drive 文件搜索、Contacts 联系人、Sheets 读写、Docs 导出，需 OAuth 授权 |

### ✉️ 邮件

| 技能           | 说明                                                                                         |
| -------------- | -------------------------------------------------------------------------------------------- |
| `agently-mail` | 通过 agently-cli 操作邮件：发送、回复、转发、搜索、读取、下载附件和管理收件箱，写操作需二次确认 |

### 📚 Obsidian

| 技能                | 说明                                                                        |
| ------------------- | --------------------------------------------------------------------------- |
| `obsidian-cli`      | 命令行操作 Obsidian 笔记库：读写笔记、搜索、管理任务/属性，支持插件开发调试 |
| `obsidian-markdown` | Obsidian 风味 Markdown：wikilink、嵌入、callout、属性等特有语法             |

### ☕ 生活服务

| 技能        | 说明                                                                                     |
| ----------- | ---------------------------------------------------------------------------------------- |

### 🛠️ 开发 & 最佳实践

| 技能             | 说明                                                                                  |
| ---------------- | ------------------------------------------------------------------------------------- |
| `skill-creator`  | 创建新技能、修改/改进现有技能、测量技能性能，支持评估和迭代                           |
| `find-skills`    | 搜索和安装开放技能生态中的技能包，帮助发现可扩展的 Agent 能力                         |
| `dirs-submit`    | ship CLI，封装 aidirs.org 和 backlinkdirs.com 的登录、预览、提交与自更新流程        |
| `repo-analyzer`  | 分析代码仓库的架构、技术栈、核心模块和风险，生成结构化项目分析报告（Markdown + HTML） |
| `issue-analyzer` | 分析崩溃堆栈、日志和源代码，生成根因分析报告，含调用链、修复建议（Markdown + HTML）   |
| `domain-handler` | 域名注册/查询与 Cloudflare DNS 自动接入工作流，统一处理 Spaceship、Cloudflare、Vercel 等域名相关操作 |
| `add-locale` | 添加或补齐 Humanizer locale，本地化覆盖、注册表、共享引擎和测试需达到完整 parity |
| `mkfast-env-init` | 初始化 mkfast-template 及其 fork 的环境变量，避免乱造 key、混用 build/runtime config 或覆盖 secrets |
| `guizang-social-card-skill` | Generate Guizang-style social card image sets and WeChat official account cover pairs from articles, scripts, screenshots, product notes, subtitles, or photos. Use when the user asks for 小红书图文, Rednote/Xiaohongshu images, social cards, carousel images, 3:4 covers, 微信公众号封面, WeChat 21:9 + 1:1 covers, Swiss Style, or magazine-style social images. |
