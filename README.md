<div align="center">

**English** | [简体中文](./README.zh-CN.md)

# Stoic

**LL.B. candidate @ Zhongnan University of Economics and Law × self-taught engineer**

I build tools for the parts of law that software is actually good at — **rules, texts, verification** —  
and stay candid about the parts it cannot do — **judgment, accountability, the last mile of trust**.

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

I take pain points that genuinely exist in legal practice and turn them into engineering problems of the form
**data → structured constraints → LLM / Agent → human review**:

- **Not free-form generation.** Official scoring rubrics, glossaries and statute texts are structured *first*; the model then checks, fills or drafts against them.
- **Not a single prompt.** Multi-subagent review loops plus hard verification gates — the pipeline would rather fail loudly than ship a fake green light.
- **Not pretending the model is omnipotent.** Every project documents its applicable boundary and the exact spot where a human takes over.

---

## Featured work

<table>
<tr>
<td width="50%" valign="top">

### 🏛️ [cn-judbench](https://github.com/1438388098-glitch/cn-judbench)
**CN-JudBench (法衡) — an open benchmark for LLMs on Chinese judicial tasks**

- 12 task packs, 323 items, versioned and growing
- Machine-checked scoring, not LLM-as-judge vibes
- Pre-registered statistical protocol before each release
- Code MIT · public data CC BY 4.0

`Benchmark` · `Evaluation` · `Reproducibility`

</td>
<td width="50%" valign="top">

### ⚖️ [fakao-grader](https://github.com/1438388098-glitch/fakao-grader)
**AI grader for the essay round of China's legal professional exam (Agent Skill)**

- Point-by-point scoring against the official rubric — not an impression score
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
- Six-dimension multi-subagent review loop; P0 findings must be fixed and re-reviewed
- Atomic writes / process locks / login state stays local

`Multi-Agent` · `Playwright` · `PDF Pipeline`

</td>
<td width="50%" valign="top">

### 🔍 [statute-rag](https://github.com/1438388098-glitch/statute-rag)
**Hybrid retrieval base for statutes — with honest eval numbers**

- Structured chunking → LIKE / BM25 / RRF fusion → forced article-level citations
- Offline evaluation fully reproducible: **Recall@5 98.9% vs 77.4% lexical baseline**
- Semantic-vector channel on the roadmap, behind the same eval harness

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

- Full texts of 260+ Chinese laws and regulations, SQLite FTS5 search with highlighting
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
| [legal-hallu-guard](https://github.com/1438388098-glitch/legal-hallu-guard) | Citation guardrails for legal answers — existence, quotation fidelity, assertion coverage; the wrong-citation rate is *measured*, not assumed |
| [fakao-shuati](https://github.com/1438388098-glitch/fakao-shuati) | Self-hosted essay-exam practice platform — AI grading against scoring points, deep review reports, kanban & error book, zero native deps |
| [legal-job-tracker](https://github.com/1438388098-glitch/legal-job-tracker) | Legal-hiring information platform — 33 official sources, dedup, résumé matching, application tracking; runs locally, data never leaves the machine |
| [level-design-master](https://github.com/1438388098-glitch/level-design-master) | AI skill for 2D / metroidvania level design, with deterministic verification gates |

Also in private repos: a quant data platform (A-share market data engineering) and a community-sentiment pipeline — architecture and trade-offs available on request.

---

## How I think about the limits of LLMs in law

These four rules are what I actually enforce in code — and the part of my work I most welcome questions about:

1. **Structure before generation.** Scoring points, glossaries and statute texts are structured first; the model compares, fills and drafts against them — it does not score end-to-end like a black box.
2. **Verifiable beats fluent.** Page coverage, score totals and term backfill are checked by scripts. I would rather the pipeline crash than output something that merely *looks* complete.
3. **Human review is not optional.** Model output is positioned as first draft / assisted scoring / retrieval summary; final authority stays with official rules and human experts.
4. **Hallucination must be traceable.** Citations keep anchors to the original text; medium/low confidence triggers forced re-review; anomalies are never silently swallowed.

---

## Now

- Final-year LL.B. coursework & preparing for the essay round of the National Legal Professional Qualification Exam (法考)
- Growing [cn-judbench](https://github.com/1438388098-glitch/cn-judbench): more task packs, a reproducible leaderboard, a first technical report

## Contact

- Open to conversations about legal tech, computational law and LLM evaluation — research collaboration especially welcome
- Wherever exams, statutes or data are involved, official channels and human judgment prevail; AI output here is assistance only — not legal advice, not official scoring

<div align="center">

*"First be clear about where the model fails — then decide where to let it help."*

</div>
