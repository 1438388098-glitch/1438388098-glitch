<div align="center">

# Stoic

**法律场景 LLM 应用实践｜可复核 · 可评估 · 懂边界**

用 Agent / LLM 把法律领域里「重规则、重文本、重复核」的流程做成可运行的工具  
在跑产品 · 在写 Skill · 在踩坑并记录边界

`法律科技` · `LLM 应用工程` · `检索增强 / 评测` · `人机复核`

![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6%2B-F7DF1E?logo=javascript&logoColor=black)
![LLM](https://img.shields.io/badge/LLM-DeepSeek%20%7C%20OpenAI%20%7C%20Zhipu-8A2BE2)
![Agent](https://img.shields.io/badge/Agent-Multi--Agent%20%7C%20Skill-FF6B35)
![Legal Tech](https://img.shields.io/badge/Domain-Legal%20Tech-1B4F72)

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

### ⚖️ [fakao-grader](https://github.com/1438388098-glitch/fakao-grader)
**法考主观题 AI 评卷老师（Agent Skill）**

按官方采分点逐点判分，不是印象分：
- 采分点三类标注（结论 / 依据 / 分析）
- 连锁丢分依赖链可视化
- 双分数：训练口径 + 考场预估带
- 判分稳定性：校准样例 + 置信度 + 中置信二次复核

`Agent` · `Legal EdTech` · `Scoring Rubric`

</td>
<td width="50%" valign="top">

### 📚 [zhuma-fakao-review](https://github.com/1438388098-glitch/zhuma-fakao-review)
**法考错题 → 可背诵知识笔记 PDF**

全量错题抓取后，按知识点合并去重，生成分册 PDF：
- 多 subagent「科目 × 维度」六维审查闭环
- P0 必须修订并复审，解析失败直接报错
- 原子落盘 / 进程锁 / 登录态只留本地

`Multi-Agent` · `Playwright` · `PDF Pipeline`

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

### 🔍 [legal-wisdom-app](https://github.com/1438388098-glitch/legal-wisdom-app)
**法律智库 · 250+ 部法条检索 + AI 问答**

法条全文检索增强的法律问答桌面应用：
- SQLite FTS5 全文检索 + 关键词高亮
- 阅读时「结合当前法条」向模型提问
- 法条关联推荐与一键跳转

`FTS5 检索增强` · `PySide6` · `LLM API`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🔁 [auto-iterate-project](https://github.com/1438388098-glitch/auto-iterate-project)
**项目自动迭代工作流（Agent 工程方法论）**

让 Agent 长时间无人值守改造仓库的工程化尝试：
- 待办池按价值/风险排序，每轮实现即验证
- 确定性校验门禁 + LLM 提案分离，拒绝假绿灯
- 方向预测带证据校验，失败假设不回流污染统计

`Agent Workflow` · `Deterministic Gate` · `Methodology`

</td>
<td width="50%" valign="top">

### 📊 数据工程实践（私有仓库）

量化数据中台与社群情绪 Pipeline，两套可调度的数据系统：
- 千万级日线中台：采集 → 调度 → 质量门禁 → 信号产出
- 情绪监控：消息采集 → 打标分析 → 每日指数看板

因涉及实盘策略与运行细节保持私有，**架构与工程取舍欢迎面谈**。

`Data Pipeline` · `Scheduling` · `Quality Gate`

</td>
</tr>
</table>

### 更多

| 仓库 | 说明 |
|------|------|
| [level-design-master](https://github.com/1438388098-glitch/level-design-master) | 2D/银河城关卡设计 AI Skill（确定性校验门禁） |

其余小工具与实验项目已归档为私有。

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

## 正在探索

- [statute-rag](https://github.com/1438388098-glitch/statute-rag)：在 [legal-wisdom-app](https://github.com/1438388098-glitch/legal-wisdom-app) 的 FTS5 检索底座之上，升级为**带可复现评测**的法条混合检索（引用溯源、混合召回；当前词法版 Recall@5 98.9%，语义向量通道在路线图）
- Agent 在**合规审查、合同要点抽取**场景的可落地产出
- 把个人 Skill 写成可复用、可评测的小产品，而不只是本地脚本

---

## 联系与说明

- 欢迎法律科技 / 法务科技 / AI 应用方向的交流与内推
- 涉及考试、法条、数据的场景均以官方渠道与人工判断为准；AI 产出为辅助，不构成法律意见或官方评分

<div align="center">

*「先想清楚模型哪里不行，再决定哪里让它行。」*

</div>
