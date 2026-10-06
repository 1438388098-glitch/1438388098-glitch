<div align="center">

**简体中文** | [English](./README.md)

# Stoic

**中南财经政法大学 · 法学本科在读 × 自学工程**

**法律场景 LLM 应用实践**

用 Agent 和 LLM 把法律流程里规则性强、文本量大、需要反复核对的环节做成能跑的工具。有几个是我自己每天在用的产品，踩过的坑和边界都记录在各仓库里。

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

我的项目大多从自己的真实需求出发（备考、找工作），做法比较一致：先把官方采分点、术语表、法条原文整理成程序能核对的格式，再让模型在这个格式里工作；关键环节有脚本校验和多 subagent 交叉审查，校验不过宁可报错，也不输出看似完整的假结果。每个项目的适用边界和人工兜底位置都写在文档里。

---

## 精选项目

<table>
<tr>
<td width="50%" valign="top">

### 🏛️ [cn-judbench](https://github.com/1438388098-glitch/cn-judbench)
**CN-JudBench（法衡）：中国司法多维度大模型评测框架**

- 12 任务包 · 323 题，版本化持续扩充
- 判分由脚本按预登记的规则逐项核对，结果可复现
- 每次发布前执行预注册统计协议，结果可复现
- 代码 MIT · 公开数据 CC BY 4.0
- 技术报告 v1 已发布，最新 release [v0.6.1](https://github.com/1438388098-glitch/cn-judbench/releases/tag/v0.6.1)，报告作为 release 附件可下载

`Benchmark` · `评测` · `可复现性`

</td>
<td width="50%" valign="top">

### ⚖️ [fakao-grader](https://github.com/1438388098-glitch/fakao-grader)
**法考主观题 AI 评卷老师（Agent Skill）**

按官方采分点逐点判分，每个采分点可回溯：
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
- 六个维度的多 subagent 审查，问题分级处理
- P0 必须修订并复审，解析失败直接报错
- 原子落盘 / 进程锁 / 登录态只留本地

`Multi-Agent` · `Playwright` · `PDF Pipeline`

</td>
<td width="50%" valign="top">

### 🔍 [statute-rag](https://github.com/1438388098-glitch/statute-rag)
**法条混合检索底座——评测数字可复现**

- 结构化分块 → LIKE/BM25/RRF 混合召回 → 强制条文级引用
- 评测数字两套并列、不藏短：合成金标 **Recall@5 100.0%**；真实问句金标（38 条真实用户提问，来源全记录）当前 v6/v7 条文级语料 **52.6%（20/38）**，R@30 94.7%，v0.1 时为 26.3%——[每一步机制与剩余失败案例全记录](https://github.com/1438388098-glitch/statute-rag/blob/main/docs/retrieval-improvement.md)
- 可选的语义 / LLM 重排层用同一套评测脚本对比，默认关闭

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
| [headphone-logger](https://github.com/1438388098-glitch/headphone-logger) | Windows 耳机连接事件日志（.NET 10，63 项单测，仅播放时记录） |
| [PowerFlowStudio](https://github.com/1438388098-glitch/PowerFlowStudio) | 电力系统潮流计算 GUI——画布拖拽建模，pandapower 内核（牛顿-拉夫逊 / N-1 校核 / OPF / IEEE 算例库） |
| [RollingPlan](https://github.com/1438388098-glitch/RollingPlan) | 计划滚动分配桌面应用——未完成的计划自动顺延到次日，全程可撤销 |
| [playlist-analysis](https://github.com/1438388098-glitch/playlist-analysis) · [bilibili-progress-tracker](https://github.com/1438388098-glitch/bilibili-progress-tracker) | 多平台歌单分析 · B 站网课进度扩展 |
| [poetry-site](https://github.com/1438388098-glitch/poetry-site) · [personal-website](https://github.com/1438388098-glitch/personal-website) | 个人诗集站（2021 至今，纯 PHP）· 个人主页 |

</details>

### 也在做

法律之外还有两个私有项目：

- **`stock-db`**——A 股量化平台：5,824 只 A 股 / 1,674 万行日线（2000-01 至 2026-08），带新鲜度与质量门禁的每日调度，实盘 Top20 选股链（等权、半月换仓、行业 ≤4、ST/涨停过滤），实盘交易台账，外加一条 GP 因子挖掘研究线；688 项测试通过。
- **社群情绪 Pipeline**——采集 → 分析 → Fear & Greed 日报看板。

两个仓库均为私有，**架构与工程取舍欢迎交流**。

---

## 能力栈

```text
领域        法律实务流程理解 · 法考评分标准 · 法条/司法解释结构
AI 应用     Prompt / CoT 工程 · Multi-Agent 编排 · Agent Skills · 检索增强（FTS5 底座，Hybrid RAG 演进中）
工程        Python · JavaScript/Node · SQLite/FTS5 · Playwright · PDF 管线
数据        采集与清洗 · 指标定义 · 调度与门禁 · 可复现流水线
产品习惯    从真实场景倒推能力边界 · 先锁验收再扩功能 · 文档与防呆写进仓库
```

**常用 AI 产品与接口**：Claude Code / ZCode 等 Agent CLI；DeepSeek、OpenAI、智谱、SiliconFlow 等模型 API。在真实项目里对比过成本、稳定性与可审查性，选型结论写在项目文档里。

---

## 几条硬约束

这些规则在我所有项目里实际执行，欢迎追问细节：

1. 采分点、术语表、法条原文先结构化，模型负责对照、填空和起草，打分由规则从结构化证据里算出
2. 页覆盖、分值合计、术语回填都用脚本核对，校验不过程序直接失败
3. 模型产出只当作初稿、辅助判分和检索摘要，最终结论以官方规则和人的判断为准
4. 引用保留原文锚点，中低置信的结果强制复核，异常不允许静默吞掉

---

## 正在做

- 法考主观题冲刺 + 大四课业
- [cn-judbench](https://github.com/1438388098-glitch/cn-judbench)：扩充任务包、公开可复现榜单；技术报告 v1 已随 [v0.6.1](https://github.com/1438388098-glitch/cn-judbench/releases/tag/v0.6.1) 发布
- [statute-rag](https://github.com/1438388098-glitch/statute-rag)：真实问句 Recall@5 当前 52.6%（v6/v7 条文级语料，R@30 94.7%），语义 / LLM 重排可选层用同一套脚本评测

---

## 联系与说明

- 作品集：[iweistoicqc5.top](https://iweistoicqc5.top) · GitHub：[@1438388098-glitch](https://github.com/1438388098-glitch) · Email: sww00316@163.com
- 漏洞与安全问题请走 GitHub 私有漏洞报告（仓库 Security 页 → Report a vulnerability），见账号级 [SECURITY.md](https://github.com/1438388098-glitch/.github/blob/main/SECURITY.md)
- 欢迎法律科技 / 法务科技 / AI 应用方向的交流与合作
- 涉及考试、法条、数据的场景均以官方渠道与人工判断为准；AI 产出为辅助，不构成法律意见或官方评分

