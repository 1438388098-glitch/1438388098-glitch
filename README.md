<div align="center">

**English** | [简体中文](./README.zh-CN.md)

# Stoic

**LL.B. candidate @ Zhongnan University of Economics and Law × self-taught engineer**

I build tools that run the rule-heavy, text-heavy, verification-heavy parts of legal work with agents and LLMs. A few of them are products I use daily, and the pitfalls and limits I hit along the way are documented in each repo.

`Legal Tech` · `LLM Application Engineering` · `Retrieval / Evaluation` · `Human-in-the-loop`

![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6%2B-F7DF1E?logo=javascript&logoColor=black)
![Agent](https://img.shields.io/badge/Agent-Multi--Agent%20%7C%20Skill-FF6B35)
![Legal Tech](https://img.shields.io/badge/Domain-Legal%20Tech-1B4F72)
![LL.B.](https://img.shields.io/badge/LL.B.-ZUEL%2C%20final%20year-8B0000)

[![GitHub followers](https://img.shields.io/github/followers/1438388098-glitch?style=social)](https://github.com/1438388098-glitch)

</div>

---

## What I work on

My projects usually start from a real need of my own — studying for the exam, looking for a job. The approach is consistent: I turn official scoring rubrics, glossaries and statute texts into formats a program can check, let the model work inside that structure, and have scripts plus multi-subagent cross-review verify the output. When a check fails, the pipeline fails loudly. Every project documents where it applies and where a human takes over.

---

## Featured work

<table>
<tr>
<td width="50%" valign="top">

### 🏛️ [cn-judbench](https://github.com/1438388098-glitch/cn-judbench)
**CN-JudBench (法衡) — an open benchmark for LLMs on Chinese judicial tasks**

- 12 task packs, 323 items, versioned and growing
- Machine-checked scoring at the predicate level, fully auditable
- Pre-registered statistical protocol before each release
- Technical report v1 released — latest release [v0.6.1](https://github.com/1438388098-glitch/cn-judbench/releases/tag/v0.6.1), with the report attached as a downloadable asset
- Code MIT · public data CC BY 4.0

`Benchmark` · `Evaluation` · `Reproducibility`

</td>
<td width="50%" valign="top">

### ⚖️ [fakao-grader](https://github.com/1438388098-glitch/fakao-grader)
**AI grader for the essay round of China's legal professional exam (Agent Skill)**

- Point-by-point scoring against the official rubric, every point traceable
- Scoring points tagged by type (conclusion / basis / analysis), with lost-point dependency chains
- Dual output: training score + exam-day estimate band
- Stability: calibration samples, confidence levels, second-pass review at medium confidence

`Agent` · `Legal EdTech` · `Scoring Rubric`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 📚 [zhuma-fakao-review](https://github.com/1438388098-glitch/zhuma-fakao-review)
**Wrong-answer book → memorizable study notes (PDF)**

- Full scrape of my exam-app wrong answers, merged and deduped by knowledge point
- Six-dimension multi-subagent review with severity tiers; P0 findings must be fixed and re-reviewed
- Atomic writes / process locks / login state stays local

`Multi-Agent` · `Playwright` · `PDF Pipeline`

</td>
<td width="50%" valign="top">

### 🔍 [statute-rag](https://github.com/1438388098-glitch/statute-rag)
**Hybrid retrieval base for statutes — with honest eval numbers**

- Structured chunking → LIKE / BM25 / RRF fusion → forced article-level citations
- Honest eval, both numbers shown: synthetic gold **Recall@5 100.0%**; real-question gold (38 real user questions, sources logged) **52.6% (20/38)** on the current v6/v7 article-level corpus, up from 26.3% at v0.1 — [every step and leftover failures documented](https://github.com/1438388098-glitch/statute-rag/blob/main/docs/retrieval-improvement.md)
- Optional semantic and LLM reranking layers are measured with the same scripts and stay off by default

`Hybrid RAG` · `Citation Grounding` · `Offline Eval`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🌐 [pdf-legal-zh-translator](https://github.com/1438388098-glitch/pdf-legal-zh-translator)
**EN→ZH translation skill for long legal & policy PDFs**

- Built for treaty / judgment / policy documents running to hundreds of pages
- Chunked parallel translation with cross-chunk context; single-source shared glossary, race-free merging
- Citation fidelity (`§ 1983`, case names preserved) + page-coverage hard checks + multi-agent QA

`Long-doc LLM` · `Glossary Sync` · `Quality Gate`

</td>
<td width="50%" valign="top">

### 📖 [legal-wisdom-app](https://github.com/1438388098-glitch/legal-wisdom-app)
**Local statute library with retrieval-augmented Q&A**

- Full texts of 257 Chinese laws and regulations (core codes pending; the database rebuilds from public sources via docs/repro.md), SQLite FTS5 search with highlighting
- Ask the model "in light of the current article" while reading
- Related-article suggestions with one-click jump

`FTS5 RAG` · `PySide6` · `LLM API`

</td>
</tr>
</table>

### More

| Repo | What it does |
|------|--------------|
| [clause-scope](https://github.com/1438388098-glitch/clause-scope) | Contract clause extraction & risk flags — deterministic rule engine, span-level evidence, three tiers of findings (missing / unbalanced / vague) |
| [legal-hallu-guard](https://github.com/1438388098-glitch/legal-hallu-guard) | Citation guardrails for legal answers — existence, quotation fidelity, assertion coverage; on a 14,212-article real corpus: 0% false positives, 100% detection of fabricated / misquoted / uncited citations (constructed baseline) |
| [fakao-shuati](https://github.com/1438388098-glitch/fakao-shuati) | Self-hosted essay-exam practice platform — AI grading against scoring points, deep review reports, kanban & error book, zero native deps |
| [legal-job-tracker](https://github.com/1438388098-glitch/legal-job-tracker) | Legal-hiring information platform — 33 official sources, dedup, résumé matching, application tracking; runs locally, data never leaves the machine |
| [auto-iterate-project](https://github.com/1438388098-glitch/auto-iterate-project) | Autonomous project-iteration workflow — backlog ranked by value/risk, deterministic verification gates, LLM proposals kept separate |
| [level-design-master](https://github.com/1438388098-glitch/level-design-master) | AI skill for 2D / metroidvania level design, with deterministic verification gates |

<details>
<summary><strong>More public repos — engineering & life side</strong></summary>

| Repo | What it does |
|------|--------------|
| [JurisCoT](https://github.com/1438388098-glitch/JurisCoT) | Chain-of-thought prompt templates + CLI for legal thesis writing (6 thesis types, link-checked reasoning chains) |
| [zhcrypt](https://github.com/1438388098-glitch/zhcrypt) | Threshold secret-sharing & cryptography toolkit (Shamir et al.) |
| [fakao-tracker](https://github.com/1438388098-glitch/fakao-tracker) | Study tracker for the legal professional qualification exam — task calendar, check-ins, stats (data stays local) |
| [maze-game](https://github.com/1438388098-glitch/maze-game) | Gamified maze generation & pathfinding with a quantitative evaluation harness |
| [CS2D](https://github.com/1438388098-glitch/CS2D) | From-scratch 2D top-down shooter — 16 ADR-documented iterations, evolved AI bot ladder |
| [headphone-logger](https://github.com/1438388098-glitch/headphone-logger) | Windows headphone connect/disconnect event logger, records only while sound is playing (.NET 10, 63 unit tests) |
| [PowerFlowStudio](https://github.com/1438388098-glitch/PowerFlowStudio) | Power-flow calculator GUI — drag-and-drop grid editing on pandapower (Newton–Raphson, N-1 check, OPF, IEEE test cases) |
| [RollingPlan](https://github.com/1438388098-glitch/RollingPlan) | Rolling task planner desktop app — unfinished plan items auto-roll to the next day, full undo history |
| [playlist-analysis](https://github.com/1438388098-glitch/playlist-analysis) · [bilibili-progress-tracker](https://github.com/1438388098-glitch/bilibili-progress-tracker) | Multi-platform playlist analyzer · Bilibili course-progress extension |
| [poetry-site](https://github.com/1438388098-glitch/poetry-site) · [personal-website](https://github.com/1438388098-glitch/personal-website) | Personal poetry site since 2021 (plain PHP) · personal homepage |

</details>

### Also building

Beyond legal tech, two private projects:

- **`stock-db`** — an A-share quantitative platform: 5,824 stocks / 16.7M daily bars (2000-01 to 2026-08), scheduled pipelines with freshness and quality gates, a live top-20 selection chain (equal-weight, half-month rebalance, industry cap, ST/limit-up filters), a real trading ledger, and a GP factor-mining research line; 688 passing tests.
- **community-sentiment pipeline** — collection → analysis → a Fear & Greed daily dashboard.

Both are private; architecture and trade-offs available on request.

---

## Hard rules in every project

These hold across everything I ship; happy to walk through the details:

1. Scoring points, glossaries and statute texts are structured first; the model compares, fills and drafts inside that structure, and scores are computed by rules from the structured evidence.
2. Page coverage, score totals and term backfill are checked by scripts — a failed check fails the pipeline.
3. Model output counts as first draft, assisted scoring or a retrieval summary; final authority stays with official rules and human judgment.
4. Citations keep anchors to the original text; medium/low confidence triggers a forced re-review, and anomalies are never silently dropped.

---

## Now

- Final-year LL.B. coursework & preparing for the essay round of the National Legal Professional Qualification Exam (法考)
- Growing [cn-judbench](https://github.com/1438388098-glitch/cn-judbench): more task packs, a reproducible leaderboard; technical report v1 is out
- [statute-rag](https://github.com/1438388098-glitch/statute-rag): real-question Recall@5 now **52.6%** on the v6/v7 article-level corpus (R@30 94.7%); optional semantic and LLM reranking layers are measured on the same scripts

## Contact

- Portfolio site: [iweistoicqc5.top](https://iweistoicqc5.top) · GitHub: [@1438388098-glitch](https://github.com/1438388098-glitch)
- Security and vulnerability reports: GitHub private vulnerability reporting (repository Security tab → "Report a vulnerability"), described in the account-level [SECURITY.md](https://github.com/1438388098-glitch/.github/blob/main/SECURITY.md)
- Open to conversations about legal tech, computational law and LLM evaluation — research collaboration especially welcome
- Wherever exams, statutes or data are involved, official channels and human judgment prevail; AI output here is assistance only — not legal advice, not official scoring

