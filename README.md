# MATACS-TH-2026-02: AI-Assisted Proposal Triage System

**Reference:** MATACS-TH-2026-02  

**Role:** Associate Software Developer 
 
**Candidate:** Moiz Ali

**Time spent:** Approximately 60 minutes  

---

## Repository Structure

| File / Folder | Description |
|---|---|
| [README.md](./README.md) | This file. Candidate info, AI usage note, and file index. |
| [WRITEUP.md](./WRITEUP.md) | Answers to the five design questions (under 1,000 words). |
| [PROMPTS.md](./PROMPTS.md) | Production-ready system and user prompts for extraction and scoring. |
| [ranking.json](./ranking.json) | Expected ranking of proposals A through E with statuses and scores. |
| [diagram/](./diagram/) | Process-flow diagram from upload to ranked output. |

---

## How I Used AI Tools

I used Claude (Anthropic) to draft initial structures for the prompt templates in `PROMPTS.md` and to sense-check the scoring rubric logic in `WRITEUP.md`. I disagreed with its first draft of the extraction prompt because it placed the proposal text inside the system prompt rather than the user turn, which would have let a malicious proposal body override system-level instructions. I moved the raw proposal text strictly to the user message and added an explicit untrusted-data framing in the system prompt to close that injection path. The scoring logic, weighted calculations, and edge-case reasoning in `ranking.json` were worked out independently and verified by hand.
