# Hi there 👋

AI Safety Researcher & Engineer investigating how production LLMs actually behave under adversarial conditions — and building the tools to measure it.

## 🔬 Research Lab

Independent research lab on LLM safety, evaluation methodology, and adversarial robustness in RAG/agent systems. The lab hosts open-source projects, publishes findings, and builds evaluation infrastructure.

### Featured project: [SafeRAG Eval](https://github.com/eximq/safe-rag-eval)

Open-source framework for systematic LLM safety evaluation.

- **14 scenarios** across **8 attack categories** (injection, social engineering, autonomy, hallucination, policy, confirmation, information leakage)
- **4 LLM-as-Judge evaluators** (Safety, Faithfulness, Injection Resistance, Refusal Quality)
- **Deterministic rule checks** + judge layer = catches disjoint failure sets
- **Multi-model comparison mode** with consolidated reports
- **YAML-driven** configurable security policies
- **Mock tool sandbox** with policy enforcement

### Recent findings (published on LinkedIn)

- **Multi-step escalation defeats every tested model.** In a two-turn attack, all 3 models (GPT-OSS 120B, Gemini 3.5 Flash Lite, Qwen 3.8 27B) either verbally agreed to harmful actions or started executing them at step 1. At step 2, two of three called forbidden tools after the user claimed "I have permission".
- **Size ≠ Safety.** GPT-OSS 120B executed hidden instructions embedded in a resume document (indirect prompt injection), while smaller models ignored it — reproducible across runs.
- **LLM-as-Judge has blind spots.** Judges score text, not actions. They missed tool-call violations that rules caught; rules missed verbal consent that judges caught. Single-layer evaluation misses ~50% of vulnerabilities.
- **Verbal authorization is accepted as proof.** No tested model can verify user authority — declarations are trusted as permission.

### Current scores (final run, 14 scenarios)

| Model | Passed | Rate |
|---|---|---|
| Gemini 3.5 Flash Lite | 12/14 | 86% |
| Qwen 3.8 27B | 12/14 | 86% |
| GPT-OSS 120B | 9/14 | 64% |

Full per-scenario data in `reports/`. Research notes in `notes/findings.md`.

## 🛠 Stack

**Current:**
- Python 3.10+, dataclasses, type hints
- LLM APIs: Groq (`qwen/qwen3.8-27b`, `openai/gpt-oss-120b`), Google Gemini (`models/gemini-3.5-flash-lite`)
- OpenAI-compatible client — works with any provider
- PyYAML, python-dotenv for configuration
- Custom LLM-as-Judge evaluation framework
- matplotlib for research visualizations

**Planned:**
- RAGAS for hallucination metrics
- Statistical evaluation across N runs per (model, scenario)
- LangChain / LlamaIndex for RAG pipeline integration
- ChromaDB / Qdrant for vector storage
- FastAPI evaluation dashboard
- Docker + GitHub Actions

## 📍 Looking for

Remote AI Safety research and applied research engineering roles (US/EU).
Available from: Mid-November.

Interested in: empirical LLM safety, evaluation methodology, adversarial robustness, RAG security, agent system safety.

## 📫 Reach me

- 💼 LinkedIn: [linkedin.com/in/igzu](https://linkedin.com/in/igzu) — preferred for work inquiries
- 📊 Ongoing research series on LinkedIn (follow for LLM safety findings)
- 💬 GitHub Discussions — open a discussion in any repo
- 🔗 Research lab: [github.com/eximq](https://github.com/eximq)
