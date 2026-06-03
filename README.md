# LinguaAI Reader

> 单 HTML 文件，双击即用。无需服务器，无需安装。  
> Single HTML file, double-click to run. No server, no installation required.

---

<details open>
<summary><b>🇨🇳 中文</b>（点击切换至 English ▼）</summary>

<br>

## 📖 简介

LinguaAI Reader 是一个 AI 驱动的语言学习阅读器，单 HTML 文件即可运行。通过 AI 分析词汇和句子，帮助阅读外文文章、积累词汇、巩固复习。

---

## 🚀 快速开始

### 1. 配置 API

首次使用需在右上角「配置」中填写 OpenAI 兼容接口信息：

| 字段 | 说明 | 示例 |
|------|------|------|
| **API Key** | 你的 API 密钥（仅保存在本地浏览器） | `sk-...` |
| **Base URL** | OpenAI 兼容接口地址 | `https://api.deepseek.com` |
| **Model** | 模型名称 | `deepseek-chat` |

支持 DeepSeek、OpenAI、Qwen、Moonshot、Gemini（代理）、Ollama 本地模型等。填写后点击「测试连接」验证。

---

### 2. 生成文章

侧边栏「生成文章」区域提供快速模板：

| 按钮 | 内容 |
|------|------|
| 雅思文章 | 雅思 7 分水平，300-400 词 |
| 四六级文章 | 四六级水平，250-350 词 |
| 中文阅读 | HSK4-5 级，含成语/固定搭配 |
| 商务英语 | 商务场景，300-400 词 |
| 自定义 | 自由输入提示词，可选择中/英文 |

生成的文章自动保存到文章历史。

---

### 3. 阅读文章

文章中的每个词自动拆分为可交互的 **token**。

#### 鼠标悬停
- 已分析过的词汇 → 显示蓝色虚线下划线
- 鼠标悬停 → 弹出**跨语言释义**工具条（中文词→英文释义，英文词→中文释义）
- 离开 → 工具条消失

#### 单词模式（默认）
在 AI 批注面板中点击任意词汇 → 右侧显示：
- 词性、国际音标
- 跨语言释义
- 同义词 / 反义词
- 例句（含翻译）
- 常用搭配
- 常见衍生短语
- 长难句例子
- 使用频率（★ 星级）
- 原文句子

#### 句子模式
AI 批注面板标题右侧切换到「句子」模式 → 点击任意词汇 → AI 分析整句话：
- 语法结构、句子主干、从句拆解
- 中文翻译、简单改写、写作技巧

#### 深度扩展
在批注中点击「更多学习」→ AI 额外生成近义词辨析、使用场景、常见错误、记忆技巧、地道用法。

---

### 4. 高亮笔刷

头部「笔刷」按钮，用于标记重点词汇。

| 操作 | 效果 |
|------|------|
| 单击「笔刷」开启 | 文章进入笔刷模式 |
| **单击单个词** | 该词所有出现位置同步高亮 |
| **按住拖选任意文本** | 选区连续高亮（四角圆滑） |
| 再次点击「关闭笔刷」 | 退出笔刷模式，高亮保留 |
| 侧边栏「清除高亮」 | 一键移除所有高亮 |

特点：跨页面刷新保留、切换文章时自动恢复。

---

### 5. 单词本

右上角「单词本」按钮。

#### 添加单词
点击批注中的「+ 加入单词本」→ 保存完整 AI 批注内容（释义、同反义词、衍生短语、长难句、搭配等）。

#### 时间段筛选
```
[起始日期] 至 [结束日期] [筛选] [复习模式]
```

---

### 6. 复习模式

在单词本中筛选后点击「复习模式」。

#### 流程
1. 显示当前词汇 + 词性 + 进度
2. 输入翻译 → 回车或点击「确认」
3. **正确** → 绿色反馈，自动下一个
4. **错误** → 红色反馈，显示正确答案
5. **跳过** → 计为错误，直接下一个

#### 完成
- 显示正确率 + 所有答错词汇
- 可选「复习错词」重新练习
- 可选「生成巩固文章」

错误追踪：答错的词自动记录 `wrongCount`。

---

### 7. 巩固文章（RAG）

复习完成后点击「生成巩固文章」→ AI 根据所有答错词汇生成有逻辑的故事：
- 使用 80%+ 目标词汇并**加粗**标记
- 200-300 词，有标题
- 自动进入文章历史

---

### 8. 导入 / 导出

#### 导入文章
侧边栏「文章历史」→「导入文章」，支持 `.txt` / `.md` / `.docx`。

#### 导出数据
顶部「导出」按钮：导出当前文章（TXT/Markdown）或导出全部数据（JSON 备份）。

---

### 9. 文章历史

侧边栏「文章历史」区域，每次生成/导入自动保存，点击切换，最多 100 条。

---

### 10. 语音朗读

| 操作 | 功能 |
|------|------|
| 文章区右上角 🔊 按钮 | 单击朗读/再次单击停止 |
| 批注中的 🔊 按钮 | 朗读单词 |
| 批注中的「朗读句子」 | 朗读原文句子 |

使用浏览器内置 TTS（SpeechSynthesis API）。

---

### 11. 语言切换

右上角 🌐 按钮，支持中文/英文界面切换。所有界面文字、批注标签、tooltip 即时更新。

---

## 💾 数据存储

所有数据仅保存在浏览器本地 `localStorage`，不发送到任何服务器（除 AI API 调用外）。

| 键 | 内容 |
|-----|------|
| `linguaai_config` | API 配置 |
| `linguaai_wordbook` | 单词本（含批注全文） |
| `linguaai_annotations` | AI 批注记录 |
| `linguaai_sentences` | 句子分析记录 |
| `linguaai_article` | 当前文章 HTML |
| `linguaai_article_history` | 文章历史列表 |
| `linguaai_highlights` | 高亮标记数据 |

---

## 🛠 技术架构

- 纯原生 HTML + CSS + JavaScript，零依赖
- 所有 AI 调用通过 OpenAI 兼容接口
- 事件委托处理所有词交互
- 双模式：单词分析 + 句子分析
- 响应式布局，适配桌面/平板/手机

</details>

---

<details>
<summary><b>🇬🇧 English</b>（Click to expand ▼）</summary>

<br>

## 📖 Introduction

**LinguaAI Reader** is an AI-powered language learning reader in a single HTML file. It helps you read foreign articles, build vocabulary, and reinforce learning through AI-driven word and sentence analysis.

---

## 🚀 Quick Start

### 1. Configure API

Fill in your OpenAI-compatible API info via the **Config** button (top-right):

| Field | Description | Example |
|-------|-------------|---------|
| **API Key** | Your API key (stored locally only) | `sk-...` |
| **Base URL** | OpenAI-compatible endpoint | `https://api.deepseek.com` |
| **Model** | Model name | `deepseek-chat` |

Supports DeepSeek, OpenAI, Qwen, Moonshot, Gemini (proxy), Ollama local models, etc. Click **Test Connection** to verify.

---

### 2. Generate Articles

The sidebar provides quick generation templates:

| Button | Content |
|--------|---------|
| IELTS | Band 7 level, 300-400 words |
| CET-4/6 | College English Test level, 250-350 words |
| Chinese | HSK 4-5, with idioms |
| Business | Business scenarios, 300-400 words |
| Custom | Custom prompt, Chinese/English |

Generated articles are automatically saved to history.

---

### 3. Reading

Every word in the article is split into interactive **tokens**.

#### Hover
- Analyzed words → blue dotted underline
- Hover → **cross-language translation** tooltip (Chinese word→English, English word→Chinese)
- Leave → tooltip disappears

#### Word Mode (default)
Click any word → right panel shows:
- Part of Speech, IPA
- Cross-language definition
- Synonyms / Antonyms
- Example sentence (with translation)
- Collocations
- Derivative Phrases
- Complex sentence examples
- Frequency rating
- Original sentence

#### Sentence Mode
Switch to **Sentence** mode in the annotation panel header → click a word → AI analyzes the whole sentence:
- Structure, Main Clause, Clause Analysis
- Translation, Paraphrase, Writing Tip

#### Deep Learning
Click **More Learning** → AI generates synonym differentiation, usage scenarios, common mistakes, memory tips, idiomatic usage.

---

### 4. Highlighter

Use the **Brush** button (header) to highlight key words.

| Operation | Effect |
|-----------|--------|
| Click to enable | Enters brush mode |
| **Click a word** | Highlights all occurrences |
| **Drag-select text** | Continuous highlight (rounded corners) |
| Click again to disable | Exits brush mode, highlights persist |
| Sidebar "Clear Highlights" | Removes all highlights |

Features: persists across page refreshes, auto-restored when switching articles.

---

### 5. Word Book

Click **Word Book** (top-right header).

#### Add Words
Click **Save to Word Book** in the annotation → saves full AI annotation content (definition, synonyms, derivatives, complex sentences, collocations, etc.).

#### Date Filter
```
[Start Date] to [End Date] [Filter] [Review]
```

---

### 6. Review Mode

Filter words in Word Book, then click **Review**.

#### Flow
1. Show word + POS + progress
2. Type translation → Enter or **Check**
3. **Correct** → green feedback, auto-advance
4. **Wrong** → red feedback, shows correct answer
5. **Skip** → counted as wrong, move on

#### Completion
- Shows accuracy rate + wrong words
- **Review Wrong Words** to retry
- **Generate Article** to create a reinforcement story

Error tracking: wrong words automatically track `wrongCount`.

---

### 7. Reinforcement Article (RAG)

After review, click **Generate Article** → AI creates a story using all wrong words:
- 80%+ target words, **bolded**
- 200-300 words with title
- Auto-saved to history

---

### 8. Import / Export

#### Import
**Article History** → **Import**, supports `.txt` / `.md` / `.docx`.

#### Export
**Export** button: Export current article (TXT/Markdown) or Export all data (JSON backup).

---

### 9. Article History

Sidebar **Article History** section. Auto-saved on generate/import, click to switch, max 100 entries.

---

### 10. Text-to-Speech

| Operation | Function |
|-----------|----------|
| Top-right 🔊 icon | Toggle play/stop |
| Annotation 🔊 icon | Pronounce word |
| Annotation "Listen" button | Read original sentence |

Uses browser built-in TTS (SpeechSynthesis API).

---

### 11. Language Switch

🌐 button (top-right) to toggle between Chinese and English UI. All UI text, annotation labels, and tooltips update instantly.

---

## 💾 Data Storage

All data is stored in browser `localStorage` only, never sent to any server (except AI API calls).

| Key | Content |
|-----|---------|
| `linguaai_config` | API configuration |
| `linguaai_wordbook` | Word book (full annotations) |
| `linguaai_annotations` | AI annotation records |
| `linguaai_sentences` | Sentence analysis records |
| `linguaai_article` | Current article HTML |
| `linguaai_article_history` | Article history |
| `linguaai_highlights` | Highlight data |

---

## 🛠 Tech Stack

- Vanilla HTML + CSS + JavaScript, zero dependencies
- All AI calls via OpenAI-compatible API
- Event delegation for all word interactions
- Dual mode: Word analysis + Sentence analysis
- Responsive layout (desktop / tablet / mobile)

</details>
