<div align="center">

**简体中文** | [English](./README.md)

# Stoic

**中南财经政法大学 · 法学本科在读 × 自学工程**

**法律场景 LLM 应用实践｜可复核 · 可评估 · 懂边界**

用 Agent / LLM 把法律领域里「重规则、重文本、重复核」的流程做成可运行的工具  
在跑产品 · 在写 Skill · 在踩坑并记录边界

`法律科技` · `LLM 应用工程` · `检索增强 / 评测` · `人机复核`

![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6%2B-F7DF1E?logo=javascript&logoColor=black)
![Agent](https://img.shields.io/badge/Agent-Multi--Agent%20%7C%20Skill-FF6B35)
![Legal Tech](https://img.shields.io/badge/Domain-Legal%20Tech-1B4F72)
![LL.B.](https://img.shields.io/badge/LL.B.-ZUEL%2C%20final%20year-8B0000)

[![GitHub followers](https://img.shields.io/github/followers/1438388098-glitch?style=social)](https://github.com/1438388098-glitch)

</div>

---

## 我在做什么

把法律实务里真实存在的痛点，拆成「数据 → 结构化约束 → LLM/Agent → 人工复核」的工程问题：

- **不是让模型自由发挥**，而是先把官方采分点、术语表、法条原文变成可校验的中间结构
- **不是单点 prompt**，而是多 subagent 并行审查 + 硬校验门禁，宁可报错也不产出假绿灯
- **不假装模型无所不能**——每个项目都写清适用边界与人工兜底位

---

## 精选项目

<table>
<tr>
<td width="50%" valign="top">

### 🏛️ [cn-judbench](https://github.com/1438388098-glitch/cn-judbench)
**CN-JudBench（法衡）：中国司法多维度大模型评测框架**

- 12 任务包 · 323 题，版本化持续扩充
- 机检判分，不做「LLM 当裁判」的印象分
- 每次发布前执行预注册统计协议，结果可复现
- 代码 MIT · 公开数据 CC BY 4.0
- 技术报告 v1 已随 [v0.6.0](https://github.com/1438388098-glitch/cn-judbench/releases/tag/v0.6.0) 发布

`Benchmark` · `评测` · `可复现性`

</td>
<td width="50%" valign="top">

### ⚖️ [fakao-grader](https://github.com/1438388098-glitch/fakao-grader)
**法考主观题 AI 评卷老师（Agent Skill）**

按官方采分点逐点判分，不是印象分：
- 采分点三类标注（结论 / 依据 / 分析）
- 连锁丢分依赖链可视化
- 双分数：训练口径 + 考场预估带
- 判分稳定性：校准样例 + 置信度 + 中置信二次复核

`Agent` · `Legal EdTech` · `Scoring Rubric`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 📚 [zhuma-fakao-review](https://github.com/1438388098-glitch/zhuma-fakao-review)
**法考错题 → 可背诵知识笔记 PDF**

全量错题抓取后，按知识点合并去重，生成分册 PDF：
- 多 subagent「科目 × 维度」六维审查闭环
- P0 必须修订并复审，解析失败直接报错
- 原子落盘 / 进程锁 / 登录态只留本地

`Multi-Agent` · `Playwright` · `PDF Pipeline`

</td>
<td width="50%" valign="top">

### 🔍 [statute-rag](https://github.com/1438388098-glitch/statute-rag)
**法条混合检索底座——评测数字可复现**

- 结构化分块 → LIKE/BM25/RRF 混合召回 → 强制条文级引用
- 评测数字两套并列、不藏短：合成金标 **Recall@5 98.9%**；真实问句金标（38 条真实用户提问，来源全记录）**26.3% → 44.7%**（法律口语↔法言法语同义词典 + 查询扩展）——[每一步机制与剩余失败案例全记录](https://github.com/1438388098-glitch/statute-rag/blob/main/docs/retrieval-improvement.md)
- 语义向量通道在路线图上，走同一套评测门禁

`Hybrid RAG` · `引用溯源` · `离线评测`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🌐 [pdf-legal-zh-translator](https://github.com/1438388098-glitch/pdf-legal-zh-translator)
**政治/法律长文 PDF 英→中专业翻译 Skill**

面向数百页条约、判决、政策文件：
- 按章节分块并行翻译 + 跨块上下文
- 共享术语表唯一真源，并发合并无竞态
- 法条引用保真（`§ 1983`、判例名原样保留）
- 页覆盖硬校验 + 多 agent 质量审查

`Long-doc LLM` · `Glossary Sync` · `Quality Gate`

</td>
<td width="50%" valign="top">

### 📖 [legal-wisdom-app](https://github.com/1438388098-glitch/legal-wisdom-app)
**法律智库 · 257 部法条检索 + AI 问答**

法条全文检索增强的法律问答桌面应用：
- SQLite FTS5 全文检索 + 关键词高亮
- 阅读时「结合当前法条」向模型提问
- 法条关联推荐与一键跳转

`FTS5 检索增强` · `PySide6` · `LLM API`

</td>
</tr>
</table>

### 更多

| 仓库 | 说明 |
|------|------|
| [clause-scope](https://github.com/1438388098-glitch/clause-scope) | 合同条款抽取与风险提示——确定性规则引擎，条款分类 + span 回跳 + 三级风险发现（缺失/失衡/含糊） |
| [legal-hallu-guard](https://github.com/1438388098-glitch/legal-hallu-guard) | 法律答案引用护栏——引用存在性 / 引文保真 / 断言覆盖三类确定性校验；14,212 条真实语料基线：误报 0%、三类错误引用检出均 100%（构造评测） |
| [fakao-shuati](https://github.com/1438388098-glitch/fakao-shuati) | 法考主观题自托管刷题平台——AI 按采分点批改、深度复盘报告、看板/错题本/背诵，零原生依赖 |
| [legal-job-tracker](https://github.com/1438388098-glitch/legal-job-tracker) | 法学招聘信息中台——33 个官方源自动采集、去重、简历匹配推荐、投递跟踪，单机运行数据不出本机 |
| [auto-iterate-project](https://github.com/1438388098-glitch/auto-iterate-project) | 项目自动迭代工作流——待办按价值/风险排序，确定性校验门禁 + LLM 提案分离 |
| [level-design-master](https://github.com/1438388098-glitch/level-design-master) | 2D / 银河城关卡设计 AI Skill（确定性校验门禁） |

<details>
<summary><strong>更多公开项目——工程与生活侧</strong></summary>

| 仓库 | 一句话 |
|------|--------|
| [JurisCoT](https://github.com/1438388098-glitch/JurisCoT) | 法律论文 CoT 提示模板 + 链路核对 CLI（6 类论文模板） |
| [zhcrypt](https://github.com/1438388098-glitch/zhcrypt) | 门限秘密分享与加密工具集（Shamir 等） |
| [fakao-tracker](https://github.com/1438388098-glitch/fakao-tracker) | 法考备考追踪：任务日历、打卡与统计（数据本地自备） |
| [maze-game](https://github.com/1438388098-glitch/maze-game) | 迷宫生成与寻路算法的游戏化实现（量化指标评测） |
| [CS2D](https://github.com/1438388098-glitch/CS2D) | 自研 2D 俯视角射击游戏：16 轮 ADR 迭代 + 进化 AI 对战 |
| [headphone-logger](https://github.com/1438388098-glitch/headphone-logger) | Windows 耳机连接事件日志（.NET 10，62 项单测） |
| [playlist-analysis](https://github.com/1438388098-glitch/playlist-analysis) · [bilibili-progress-tracker](https://github.com/1438388098-glitch/bilibili-progress-tracker) | 多平台歌单分析 · B 站网课进度扩展 |
| [poetry-site](https://github.com/1438388098-glitch/poetry-site) · [personal-website](https://github.com/1438388098-glitch/personal-website) | 个人诗集站（2021 至今，纯 PHP）· 个人主页 |

</details>

私有仓库中另有量化数据中台与社群情绪 Pipeline 两套数据系统，**架构与工程取舍欢迎交流**。

---

## 能力栈

```text
领域        法律实务流程理解 · 法考评分标准 · 法条/司法解释结构
AI 应用     Prompt / CoT 工程 · Multi-Agent 编排 · Agent Skills · 检索增强（FTS5 底座，Hybrid RAG 演进中）
工程        Python · JavaScript/Node · SQLite/FTS5 · Playwright · PDF 管线
数据        采集与清洗 · 指标定义 · 调度与门禁 · 可复现流水线
产品习惯    从真实场景倒推能力边界 · 先锁验收再扩功能 · 文档与防呆写进仓库
```

**常用 AI 产品与接口**：Claude Code / ZCode 等 Agent CLI；DeepSeek、OpenAI、智谱、SiliconFlow 等模型 API。在真实项目里对比过成本、稳定性与可审查性，而不是只停留在会聊天。

---

## 我如何理解 LLM 能力边界

这是我做法律 AI 时的硬约束，也是简历里愿意被追问的部分：

1. **结构先于生成**——采分点、术语表、法条原文先结构化，再交给模型对照/填空，而不是端到端黑盒打分
2. **可校验优于好听**——页覆盖、分值合计、术语回填用脚本硬校验；宁可 pipeline 失败，也不输出「看起来很完整」的假结果
3. **人审不可省**——模型产出定位为「初稿 / 辅助判分 / 检索摘要」，最终解释权仍在官方规则与人类专家
4. **幻觉要可追责**——引用保留原文锚点，中低置信强制复核，禁止静默吞掉异常

---

## 正在做

- 法考主观题冲刺 + 大四课业
- [cn-judbench](https://github.com/1438388098-glitch/cn-judbench)：扩充任务包、公开可复现榜单；技术报告 v1 已随 [v0.6.0](https://github.com/1438388098-glitch/cn-judbench/releases/tag/v0.6.0) 发布
- [statute-rag](https://github.com/1438388098-glitch/statute-rag)：真实问句检索继续推进（已 26.3% → 44.7%），下一站语义向量通道

---

## 联系与说明

- 欢迎法律科技 / 法务科技 / AI 应用方向的交流与合作
- 涉及考试、法条、数据的场景均以官方渠道与人工判断为准；AI 产出为辅助，不构成法律意见或官方评分

<div align="center">

*「先想清楚模型哪里不行，再决定哪里让它行。」*

</div>
