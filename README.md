# LinguaAI Reader

> 🚀 一款 AI 驱动的英语阅读学习系统 — 单 HTML 文件，双击即用，无需服务器、无需安装。
> 🚀 An AI-powered English reading & learning system — single HTML file, double-click to run. No server, no installation required.

---

<details open>
<summary><b>🇨🇳 中文</b> | 点击展开 English 版</summary>

<br>

## 📖 简介

LinguaAI Reader 是一款专为英语学习者打造的 AI 阅读工具。单个 HTML 文件包含完整的学习系统：AI 驱动的文章生成、智能查词、句子分析、生词本管理和间隔复习 — 全部在浏览器本地运行。

---

## 🚀 快速开始

### 1. 配置 API

在设置中填入任意兼容 OpenAI 接口的服务商信息：

| 字段 | 说明 | 示例 |
|------|------|------|
| **API Key** | 你的 API 密钥，完全存储在你自己的浏览器中 | `sk-...` |
| **Base URL** | OpenAI 兼容接口地址 | `https://api.deepseek.com` |
| **Model** | 模型名称 | `deepseek-chat` |

支持 DeepSeek、OpenAI、Qwen、Moonshot、Gemini 等云端模型，以及本地 Ollama 部署的开源 Llama 系列。一行配置即可切换，统一协议层适配所有服务商。

---

### 2. 文章来源 & 文章生成

#### 文章来源
内置丰富的英语学习资源库，通过内置代理获取原文，并自动提取正文转换为纯净阅读视图。**中文 UI 下获取英文资源，英文 UI 下获取中文资源**，切换语言后资源列表也自动适配。

- BBC Learning English、VOA、British Council、Smithsonian、NASA、Reuters、AP、NPR
- CET 四六级 / 考研 / 专四专八历年真题文本 + 答案
- 支持粘贴任意文章 URL，自动提取正文
- 支持导入本地 TXT / Markdown / PDF 文件

#### RAG 生词集成
文章生成时 AI 会读取你的生词本，智能挑选 **15 个未掌握单词**，按错误次数和查词频率排序，**自然融入文章**。复习中答对的单词自动标记"已掌握"，下一篇文章生成时优先级降低。

#### 多种 AI 文章类型
你可以选择生成不同类型的 AI 文章：

| 类型 | 说明 |
|------|------|
| 新闻文章 | 7 段式 300-400 词英语新闻 |
| 短篇故事 | 叙事风格 250-350 词 |
| 分级阅读 | HSK4-5 难度等级 / 渐进式 |
| 对话文章 | 日常对话 300-400 词 |
| 自定义 | 输入任意主题 / 关键词 |

中文 UI 生成英文文章，英文 UI 生成中文文章。自动切换，一键生成。

---

### 3. 阅读 & AI 分析

所有分析基于精确 **token** 级别，点击任意单词即时触发。

#### 阅读模式
- 原文模式：纯净阅读，点击单词弹出释义
- 显示 **未掌握生词**：自动高亮生词本中的单词，附带释义
- 显示所有生词：高亮全部生词
- 显示词性标注

#### 单词分析面板
选中任意单词后 AI 自动分析并展示：
- 音标和发音
- **词性和释义**（中文 UI 显示中文释义，英文 UI 显示英文释义）
- 同义词 / 反义词
- 例句和搭配
- 派生词
- 使用频率
- 手动添加到生词本
- 朗读发音

#### 句子分析
AI 深度解析当前句子：语法结构标注、从句拆分、句式翻译、同义改写、写作建议和词汇替换。单词分析与句子分析一键切换，结果独立缓存。

#### 生词本集成
AI 分析单词的同时，一键添加到生词本。**阅读 PDF 真题时也支持手动输入查词**，弥补 PDF 内文字不可点击的限制。

#### 高亮系统
支持点击高亮（单击单词高亮全文中所有出现位置）和拖拽高亮（选中连续文字，圆角视觉分组），多颜色可选分类标记，跨文章自动恢复。

---

### 4. 学习模式

内置多级别、多场景的学习模式，一键切换：

| 模式 | 说明 |
|------|------|
| 自由阅读 | 任意来源，自由查词和分析 |
| **CET-4 模式** | 聚焦四级考纲词汇和难度 |
| **CET-6 模式** | 聚焦六级考纲词汇和难度 |
| 考研模式 | 聚焦考研英语词汇和真题 |
| 专四专八模式 | 聚焦专四专八级别 |

各模式独立配置，互不干扰。

---

### 5. 生词本

你的个人词汇数据库，自动与 AI 系统联动。

#### 添加单词
阅读中查过的单词，一键加入生词本。系统自动记录：单词、音标、释义、首次添加时间、复习次数和错误次数。

#### 单词格式
```
[单词] · [音标] [释义] [复习次数]
```

#### 导出
- **JSON / CSV**：完整数据备份
- **PDF**：格式化 A4 词汇表

---

### 6. 复习系统

基于主动回忆的间隔复习，与 RAG 系统深度集成。

#### 流程
1. 筛选日期 + 模式 + 范围
2. 显示释义，输入翻译后按 Enter 判分
3. **正确**：标记已掌握，后续降低出现频率
4. **错误**：记录错误并显示正确答案
5. **完成**：展示正确率 + 错误清单

#### 策略
- 正确率优先 + 错误优先
- **错误单词自动提升 RAG 优先级**

复习中的 `wrongCount` 直接反馈到 RAG 生词集成系统，确保薄弱单词在下一次文章生成中获得更多曝光。

---

### 7. 导入 / 导出

#### 导入
支持从本地文件或剪贴板导入 `.txt` / `.md` / `.docx` 文章。

#### 导出
**一键导出**学习数据为 TXT/Markdown 文本，或导出完整 JSON 数据备份。

#### 真题管理
选择本地文件夹，自动扫描子目录和 PDF 文件。分类标签自动识别（CET-4 / CET-6 / 考研 / 专四 / 专八）。iframe 内嵌阅读保留原始排版、图片和表格，IndexedDB 持久化存储，刷新不丢失。支持批量多选删除已导入真题。

---

### 8. 深色模式

内置深色 / 浅色主题切换，阅读舒适度提升 100%。

---

### 9. 语音朗读

| 功能 | 说明 |
|------|------|
| 单词发音朗读 | 点击喇叭图标 / 自动播放 |
| 句子朗读播放 | 选中句子后朗读 |
| 全文自动播放 | 全篇逐句朗读 |

使用浏览器原生 TTS（SpeechSynthesis API），零带宽消耗。

---

### 10. 响应式设计

桌面端三栏布局（侧边栏 / 文章 / 分析面板），平板和手机端自动折叠为单栏，完美适配各种屏幕。

---

## 💾 数据存储

所有学习数据存储在浏览器 `localStorage` 中：

| Key | 说明 |
|-----|------|
| `linguaai_config` | API 配置 |
| `linguaai_wordbook` | 生词本，含复习次数和错误计数 |
| `linguaai_annotations` | AI 单词分析记录 |
| `linguaai_sentences` | AI 句子分析记录 |
| `linguaai_article` | 当前阅读文章 HTML |
| `linguaai_article_history` | 文章阅读历史 |
| `linguaai_highlights` | 高亮数据 |

---

## 🧰 技术栈

| 层级 | 技术方案 | 说明 |
|------|----------|------|
| **前端** | 零框架，原生 HTML5 + CSS3 + ES2020+ | 无 npm / webpack / node_modules，单文件双击即用 |
| **AI 引擎** | OpenAI 兼容接口（统一协议层） | 一行配置切换 DeepSeek / OpenAI / Qwen / Moonshot / Gemini / 本地 Ollama |
| **持久化** | localStorage + IndexedDB 双引擎 | 元数据走 localStorage（亚毫秒读取）；大型 PDF 文件走 IndexedDB（ArrayBuffer 二进制存储） |
| **PDF 阅读** | 原生 `<iframe>` + Blob URL | 历年真题 PDF 内嵌渲染，保留原始排版，无需额外渲染器 |
| **TTS 语音** | 浏览器原生 SpeechSynthesis API | 零带宽消耗，支持单词发音 + 句子朗读 + 全文 TTS |
| **事件架构** | 全局事件委托 | 数万 token 只需单个事件监听，无内存泄漏，切文章自动清理 |
| **跨语言缓存** | 内存 Map | 亚毫秒级悬停翻译，页面级即时刷新 |
| **模块设计** | 函数式 + 全局状态机 | `STATE` 对象管理 15+ 模块：生词、句子、高亮、生词本、复习、历史、真题 |
| **导出引擎** | html2pdf.js（CDN 按需加载）+ 原生 Blob | 生词本 PDF 导出 + JSON/CSV 全量备份，无需服务器 |
| **响应式布局** | Flexbox + 固定侧栏 + 弹性主区域 | 桌面端三栏（侧栏/文章/分析），平板/手机自动折叠 |

---

## 📊 市场差异化 — 为什么选择 LinguaAI

### 1. 📦 零依赖单文件 — 真正的"开箱即用"

> 大多数阅读工具需要 `npm install`、`docker compose` 或在线注册。

- **无构建工具**：不需要 webpack / vite / node.js
- **无服务器**：零数据上传，API Key 只存在于你的浏览器中
- **无数据库**：不需要 MySQL / PostgreSQL
- **双击 `index.html` 即可使用全部功能**

### 2. 🧠 RAG 生词集成 — AI "认识"你的词汇量

> 其他工具把生词本和文章生成完全割裂。

- 文章生成时 AI 读取你的生词本，智能挑选 **15 个未掌握单词**
- 按错误频率和查词次数排序，**自然编织进文章**
- 复习中答对的单词标记 "已掌握"，下次降低优先级
- 形成闭环：阅读 → 查词 → 复习 → 再阅读

### 3. 📄 原生 PDF 真题阅读 — 无需文字转换

> 大多数工具只支持纯文本，PDF 必须预先转换成 TXT/Markdown。

- **选择本地文件夹**，自动扫描子目录和 PDF 文件
- **分类标签**：CET-4 / CET-6 / 考研 / 专四 / 专八自动识别
- **内嵌 iframe 阅读**：保留原始排版、图片和表格
- **IndexedDB 持久化**：刷新页面无需重新导入
- **手动查词**：弥补 PDF 内文字不可点击的限制
- **批量删除**：多选移除已导入真题

### 4. 🔍 双模式分析 — 单词 + 句子，随时切换

> 大多数工具只提供词典查词，无法进行句子级分析。

- **单词模式**：词性、音标、释义、同反义词、例句、搭配、派生词、使用频率
- **句子模式**：语法结构、从句拆分、翻译、同义改写、写作建议
- 一键切换，结果独立缓存

### 5. 🎯 智能高亮 — 超越基础划线

- **点击高亮**：点击单词高亮全文中所有出现位置
- **拖拽高亮**：选中连续文字，圆角视觉分组
- **颜色选择器**：多种高亮颜色分类标记
- **跨文章持久化**：切换文章后高亮自动恢复

### 6. 📝 主动回忆复习 — 重新定义间隔重复

- 日期范围筛选 → 显示释义 → 输入翻译
- 正确答案自动标记"已掌握"，错误追踪计数
- 完成后展示正确率 + 错误清单
- **错误单词自动提升 RAG 优先级**，在下次文章生成中优先出现

### 7. 🌐 智能跨语言 — 中英双向切换

- 一键切换中文 / 英文 UI
- 中文 UI 学英语（查词显示中文释义）；英文 UI 学中文（查词显示英文释义）
- 悬停翻译、资源列表、生成按钮全部自动适配

### 8. 🔒 隐私优先 — 数据完全本地

- API Key 仅存储在浏览器 localStorage，永不上传
- 所有学习数据（生词、分析、历史、真题 PDF）完全留在你的设备上
- **完整 JSON 备份导出**，轻松迁移到其他设备

</details>

---

## 📖 Introduction

LinguaAI Reader is an AI-powered reading tool designed for English learners. A single HTML file packs a complete learning system: AI-driven article generation, smart dictionary lookup, sentence analysis, vocabulary management, and spaced repetition — all running locally in your browser.

---

## 🚀 Quick Start

### 1. Configure API

Fill in any OpenAI-compatible API provider in Settings:

| Field | Description | Example |
|------|------|------|
| **API Key** | Your API key, stored entirely in your own browser | `sk-...` |
| **Base URL** | OpenAI-compatible endpoint | `https://api.deepseek.com` |
| **Model** | Model name | `deepseek-chat` |

Supports DeepSeek, OpenAI, Qwen, Moonshot, Gemini, and local Ollama with open-source Llama models. One-line config to switch, unified protocol layer for all providers.

---

### 2. Article Sources & Generation

#### Article Sources
Built-in curated English learning resources. Articles are fetched via built-in proxy with automatic content extraction into clean reading view. **Chinese UI fetches English resources, English UI fetches Chinese resources** — resource lists auto-adapt on language switch.

- BBC Learning English, VOA, British Council, Smithsonian, NASA, Reuters, AP, NPR
- CET-4/6, Postgraduate Entrance Exam, TEM-4/8 past exam texts + answer keys
- Paste any article URL for automatic content extraction
- Import local TXT / Markdown / PDF files

#### RAG Vocabulary Integration
During article generation, AI reads your wordbook and intelligently selects **15 unmastered words**, sorted by error frequency and lookup count, **naturally woven into the article**. Words answered correctly in review are auto-marked "mastered" and deprioritized in the next generation.

#### AI Article Types
Choose from multiple AI-generated article types:

| Type | Description |
|------|------|
| News Article | 7-paragraph, 300-400 word English news |
| Short Story | Narrative style, 250-350 words |
| Graded Reading | HSK4-5 difficulty levels / progressive |
| Dialogue | Daily conversation, 300-400 words |
| Custom | Enter any topic / keywords |

Chinese UI generates English articles; English UI generates Chinese articles. Auto-switch, one-click generate.

---

### 3. Reading & AI Analysis

All analysis operates at precise **token** level — click any word to trigger instantly.

#### Reading Modes
- Original mode: Clean reading, click words for popup definitions
- Show **unmastered words**: Auto-highlight wordbook entries with definitions
- Show all words: Highlight every word
- Show POS tags

#### Word Analysis Panel
Select any word for AI-powered analysis:
- IPA and pronunciation
- **POS and definition** (Chinese UI shows Chinese definitions, English UI shows English definitions)
- Synonyms / antonyms
- Example sentences and collocations
- Derivatives
- Usage frequency
- One-click add to wordbook
- Pronunciation playback

#### Sentence Analysis
AI deep-parses the current sentence: grammar structure annotation, clause breakdown, translation, paraphrase, writing suggestions, and vocabulary alternatives. Word and sentence analysis toggle with one click; results independently cached.

#### Wordbook Integration
One-click add to wordbook during AI analysis. **Manual word search also supported when reading PDF exams**, bypassing the non-clickable text limitation in PDFs.

#### Highlight System
Click-to-highlight (click a word to highlight all occurrences) and drag-to-highlight (select continuous text with rounded-corner visual grouping). Multiple highlight colors for categorization. Cross-article auto-restore.

---

### 4. Learning Modes

Built-in multi-level, multi-scenario learning modes, one-click switch:

| Mode | Description |
|------|------|
| Free Reading | Any source, free lookup and analysis |
| **CET-4 Mode** | Focus on CET-4 vocabulary and difficulty |
| **CET-6 Mode** | Focus on CET-6 vocabulary and difficulty |
| Postgraduate Mode | Focus on postgraduate entrance exam vocabulary |
| TEM-4/8 Mode | Focus on TEM-4/8 level |

Each mode independently configured, no interference.

---

### 5. Wordbook

Your personal vocabulary database, automatically integrated with the AI system.

#### Adding Words
Words looked up during reading can be added to the wordbook with one click. System auto-records: word, IPA, definition, first-added timestamp, review count, and error count.

#### Word Format
```
[Word] · [IPA] [Definition] [Review Count]
```

#### Export
- **JSON / CSV**: Complete data backup
- **PDF**: Formatted A4 vocabulary list

---

### 6. Review System

Active recall-based spaced repetition, deeply integrated with the RAG system.

#### Flow
1. Filter by date + mode + range
2. Show definition, type the translation and press Enter to score
3. **Correct**: Mark mastered, deprioritize in future
4. **Incorrect**: Record error and show correct answer
5. **Complete**: Display accuracy + error list

#### Strategy
- Accuracy-first + error-priority
- **Error words auto-boosted in RAG priority**

Review `wrongCount` feeds directly into the RAG vocabulary integration system, ensuring weak words get more exposure in the next article generation.

---

### 7. Import / Export

#### Import
Import articles from local files or clipboard: `.txt` / `.md` / `.docx`.

#### Export
**One-click export** learning data as TXT/Markdown text, or export complete JSON data backup.

#### Exam Management
Select a local folder to auto-scan subdirectories and PDF files. Category tabs auto-detect (CET-4 / CET-6 / Postgraduate / TEM-4 / TEM-8). Inline iframe reading preserves original layout, images, and tables. IndexedDB persistence — no re-import after page refresh. Batch multi-select to delete imported exams.

---

### 8. Dark Mode

Built-in dark / light theme toggle for 100% reading comfort improvement.

---

### 9. Text-to-Speech

| Feature | Description |
|------|------|
| Word pronunciation | Click speaker icon / auto-play |
| Sentence reading | Select a sentence to read aloud |
| Full article TTS | Sequential sentence-by-sentence reading |

Uses browser-native TTS (SpeechSynthesis API), zero bandwidth consumption.

---

### 10. Responsive Design

Desktop 3-column layout (sidebar / article / analysis panel). Tablet and mobile auto-collapse to single column, perfectly adapted for all screen sizes.

---

## 💾 Data Storage

All learning data stored in browser `localStorage`:

| Key | Description |
|-----|------|
| `linguaai_config` | API configuration |
| `linguaai_wordbook` | Wordbook with review count and error tracking |
| `linguaai_annotations` | AI word analysis records |
| `linguaai_sentences` | AI sentence analysis records |
| `linguaai_article` | Current article HTML |
| `linguaai_article_history` | Article reading history |
| `linguaai_highlights` | Highlight data |

---

## 🧰 Tech Stack

| Layer | Technology | Notes |
|-------|------------|-------|
| **Frontend** | Zero-framework, vanilla HTML5 + CSS3 + ES2020+ | No npm / webpack / node_modules, single-file double-click to run |
| **AI Engine** | OpenAI-compatible API (universal protocol layer) | One-line config to switch: DeepSeek / OpenAI / Qwen / Moonshot / Gemini / local Ollama |
| **Persistence** | localStorage + IndexedDB dual-engine | Metadata via localStorage (sub-ms reads); large PDF files via IndexedDB (ArrayBuffer binary storage) |
| **PDF Reading** | Native `<iframe>` + Blob URL | Past exam PDFs rendered inline with original layout, no extra renderer needed |
| **TTS** | Browser-native SpeechSynthesis API | Zero bandwidth, supports word pronunciation + sentence reading + full article TTS |
| **Event Architecture** | Global event delegation | Single event listener for tens of thousands of tokens, no memory leaks, auto-cleanup on article switch |
| **Cross-language Cache** | In-memory Map | Sub-millisecond hover translation, instant page-wide refresh |
| **Module Design** | Functional + global state machine | `STATE` object manages 15+ modules: vocab, sentences, highlights, wordbook, review, history, exams |
| **Export Engine** | html2pdf.js (CDN on-demand) + native Blob | Vocab book PDF export + JSON/CSV full backup, no server needed |
| **Responsive Layout** | Flexbox + fixed sidebar + elastic main area | Desktop 3-column (sidebar/article/analysis), auto-collapse on tablet/mobile |

---

## 📊 Market Differentiators — What Makes LinguaAI Unique

### 1. 📦 Zero-Dependency Single File — Truly "Just Open It"

> Most reading tools require `npm install`, `docker compose`, or online sign-up.

- **No build tools**: No webpack / vite / node.js required
- **No server**: Zero data uploaded, API key stays in your browser
- **No database**: No MySQL / PostgreSQL needed
- **Double-click `index.html` to access every feature**

### 2. 🧠 RAG Vocab Integration — AI That "Knows" Your Vocabulary

> Other tools keep vocab books and article generation completely separate.

- AI reads your wordbook when generating articles, selects **15 unmastered words**
- Sorted by error frequency and lookup count, **naturally woven into the article**
- Words answered correctly in review are marked mastered, deprioritized next time
- Creates a closed loop: Read → Look Up → Review → Read Again

### 3. 📄 Native PDF Reading for Past Exams — No Text Conversion Needed

> Most tools only support plain text; PDFs must be pre-converted to TXT/Markdown.

- **Select a local folder**, auto-scan subdirectories and PDF files
- **Category tabs**: CET-4 / CET-6 / Postgraduate / TEM-4 / TEM-8 auto-detected
- **Inline iframe reading**: preserves original layout, images, tables
- **IndexedDB persistence**: no re-import after page refresh
- **Manual word search**: bypasses non-clickable text limitation in PDFs
- **Batch delete**: multi-select to remove imported exam papers

### 4. 🔍 Dual-Mode Analysis — Word + Sentence, Switch Anytime

> Most tools only offer dictionary lookup, no sentence-level analysis.

- **Word Mode**: POS, IPA, definition, synonyms/antonyms, examples, collocations, derivatives, frequency
- **Sentence Mode**: grammar structure, clause breakdown, translation, paraphrase, writing tips
- One-click toggle, results independently cached

### 5. 🎯 Smart Highlighter — Beyond Basic Underlining

- **Click-to-highlight**: click a word to highlight all occurrences across the article
- **Drag-to-highlight**: select continuous text with rounded-corner visual grouping
- **Color picker**: multiple highlight colors to categorize
- **Cross-article persistence**: highlights auto-restore when switching articles

### 6. 📝 Active Recall Review — Spaced Repetition Reinvented

- Date range filter → show definition → type the translation
- Correct answers auto-marked "mastered", errors tracked by count
- Completion shows accuracy + error list
- **Errors auto-boosted in RAG priority**, prioritized in next article generation

### 7. 🌐 Smart Cross-Language — Bidirectional Chinese/English

- One-click UI toggle between Chinese and English
- Chinese UI → learn English (lookups show Chinese definitions); English UI → learn Chinese (lookups show English definitions)
- Hover translations, resource lists, generation buttons all adapt automatically

### 8. 🔒 Privacy-First — Fully Local Data

- API Key stored only in browser localStorage, never uploaded
- All learning data (vocab, annotations, history, exam PDFs) stays on your device
- **Full JSON backup export** for easy migration to other devices
