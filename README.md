# 🔍 Awesome Research Agents

<p align="center">
  <a href="https://awesome.re"><img src="https://img.shields.io/badge/Awesome-%F0%9F%94%8D_Research_Agents-000000?style=for-the-badge&labelColor=000000" alt="Awesome Research Agents"></a>
  <a href="https://github.com/chrisliu298/awesome-research-agents/stargazers"><img src="https://img.shields.io/github/stars/chrisliu298/awesome-research-agents?style=for-the-badge&logo=github&logoColor=white&label=Stars&labelColor=000000&color=000000" alt="GitHub Stars"></a>
  <a href="https://github.com/chrisliu298/awesome-research-agents/network/members"><img src="https://img.shields.io/github/forks/chrisliu298/awesome-research-agents?style=for-the-badge&logo=github&logoColor=white&label=Forks&labelColor=000000&color=000000" alt="GitHub Forks"></a>
  <a href="https://github.com/chrisliu298/awesome-research-agents/commits"><img src="https://img.shields.io/github/last-commit/chrisliu298/awesome-research-agents?style=for-the-badge&logo=github&logoColor=white&label=Last%20Commit&labelColor=000000&color=000000" alt="Last Commit"></a>
</p>

Curated resources for building, evaluating, and stress-testing research agents around Claude Code, OpenAI Codex CLI, and adjacent coding-agent CLIs, with emphasis on AI/ML research workflows: literature, hypothesis design, implementation, experiments, analysis, writing, review, rebuttal, and project memory.

> If you maintain a research-agent project that should be on this list, or you spot a mistake, broken link, or stale entry, please open an issue or pull request.

## Contents

- [What this list covers](#what-this-list-covers)
- [Start Here](#start-here)
- [Research Stage Map](#research-stage-map)
- [Coding-Agent Substrates and Hosts](#coding-agent-substrates-and-hosts)
- [Skills, Workflow Packs, and Reusable Procedures](#skills-workflow-packs-and-reusable-procedures)
- [Literature Discovery and Evidence Grounding](#literature-discovery-and-evidence-grounding)
- [Lab Integrations, Notebooks, Experiment Tracking, and Memory](#lab-integrations-notebooks-experiment-tracking-and-memory)
- [Autonomous Execution Loops](#autonomous-execution-loops)
- [End-to-End Research and Hypothesis Systems](#end-to-end-research-and-hypothesis-systems)
- [Manuscript, Figure, Reproduction, and Paper-to-Agent Systems](#manuscript-figure-reproduction-and-paper-to-agent-systems)
- [Review and Rebuttal Systems](#review-and-rebuttal-systems)
- [Benchmarks and Research Arenas](#benchmarks-and-research-arenas)
- [Practitioner Reports, Methodology Essays, and Agent Frameworks](#practitioner-reports-methodology-essays-and-agent-frameworks)
- [Open Problems and Gaps](#open-problems-and-gaps)
- [Contributing](#contributing)
- [Citation](#citation)
- [License](#license)

## What this list covers

This list focuses on research agents and tools built around Claude Code, OpenAI Codex CLI, and similar coding-agent CLIs. Tags are conservative: **CLI-native** means the resource ships explicit Claude Code/Codex skills, configs, docs, or workflows; **CLI-compatible** means it can be used from these agents but is not primarily built for them; **adjacent** means it informs research-agent design without being a CLI workflow. Within each section, entries are ordered CLI-native first, then CLI-compatible, then adjacent.

## Start Here

1. **Claude Code** — learn the core Claude-native substrate: repo editing, shell use, skills, hooks, subagents, memory, and MCP.
2. **OpenAI Codex CLI / Codex** — learn the OpenAI-native substrate: local CLI, `AGENTS.md`, skills, MCP, cloud/background tasks, and parallel work.
3. **AI-Research-SKILLs** — scan the broadest reusable research-skill library before writing your own workflows.
4. **ARIS: Autonomous Research via Adversarial Multi-Agent Collaboration** — study the strongest Claude/Codex-facing autonomous research loop and its claim-audit patterns.
5. **PaperOrchestra: A Multi-Agent Framework for Automated AI Research Paper Writing** — use as the main paper-writing and figure-generation reference.
6. **PaperQA2** — add a literature-grounded retrieval layer instead of relying on model memory for citations.
7. **ResearchArena: How Far Are We From True Auto Research?** — calibrate expectations against direct Claude Code/Codex-style research-agent evaluation.
8. **Stop Automating Peer Review Without Rigorous Evaluation** — read before deploying review/rebuttal agents in high-stakes workflows.

## Research Stage Map

| Stage | Useful entries |
|---|---|
| Idea & literature | AI-Research-SKILLs, ARIS, PaperQA2, OpenScholar, STORM, ai-skill-scholar, paper-search-mcp |
| Experiment design | ARIS, The Agentic Researcher, Agent Laboratory, Towards an AI co-scientist, AAAR-1.0 |
| Coding | Claude Code, OpenAI Codex CLI / Codex, Aider, Gemini CLI, OpenHands, PaperCoder / Paper2Code |
| Execution | ARIS, W&B MCP Server, MLflow MCP Server, MLE-bench, MLAgentBench, tinyKaggleClaw |
| Analysis | Jupyter MCP Server, W&B Skills, MLflow MCP Server, data-to-paper, PaperOrchestra |
| Writing | PaperOrchestra, Agent Laboratory, The AI Scientist, data-to-paper, GPT Researcher |
| Peer review | ResearchArena (CLI-agent arena), Stanford Agentic Reviewer, AgentReview, The AI Scientist (automated review), LLM-REVal |
| Rebuttal | Paper2Rebuttal, ARIS, claude-code-my-workflow, ICML 2026 Peer Review FAQ |
| Project memory | Claude Code, OpenAI Codex CLI / Codex, Letta Code memory system, Obsidian Memory, Zotero MCP / ZotPilot, PARNESS, AgentRxiv |

## Coding-Agent Substrates and Hosts

- **[Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview)** — coding-agent CLI
  - *(2025, [CLI-native])* Terminal-native coding agent that reads repos, edits files, runs commands, and composes with `CLAUDE.md`, skills, subagents, hooks, permissions, MCP, and SDK workflows. For research, it is the main Claude substrate for experiment loops, artifact generation, lab-tool integration, and project memory.

- **[OpenAI Codex CLI / Codex](https://github.com/openai/codex)** — coding-agent CLI and cloud agent
  - *(2025, [CLI-native])* Local and cloud/background coding agent for reading, editing, and running code, with `AGENTS.md`, skills, MCP, subagents, worktrees, and parallel task support. In research workflows, Codex is useful for implementation, data analysis, evals, reports, and delegated experiment threads.

- **[OpenAI Codex cloud/background tasks](https://developers.openai.com/codex/app)** — OpenAI Developers docs
  - *(2026, [CLI-native])* Codex web/cloud mode for delegating coding tasks into isolated environments connected to GitHub, including parallel/background work. The mechanism maps naturally to ablations, eval additions, analysis threads, and report-generation tasks.

- **[Aider](https://github.com/aider-ai/aider)** — coding-agent CLI
  - *(2023, [CLI-compatible])* Terminal pair-programming agent with repo maps, file editing, lint/test loops, broad model support, and automatic git commits. It is not research-specific, but its git-native loop is useful for controlled experiment-code changes and is listed as a host by paper-writing skill packs.

- **[Gemini CLI](https://github.com/google-gemini/gemini-cli)** — coding-agent CLI
  - *(2025, [CLI-compatible])* Open-source terminal agent with file tools, shell commands, web fetching, Google Search grounding, MCP support, and `GEMINI.md` customization. It appears in multi-CLI skill-library ecosystems as a research-compatible host.

- **[OpenHands](https://github.com/OpenHands/OpenHands)** — coding-agent platform
  - *(2024, [CLI-compatible])* Model-agnostic software-agent platform with SDK, CLI, local GUI, cloud/enterprise modes, and benchmark infrastructure. It is useful when a research workflow needs programmable agent control rather than one interactive coding session.

- **[goose](https://github.com/aaif-goose/goose)** — open-source agent CLI/desktop/API
  - *(2025, [CLI-compatible])* Provider-agnostic agent for code, workflows, research, writing, automation, and data analysis, with MCP extensions, recipes, subagents, and CLI/desktop/API modes. Research-specific validation is thin, but the integration surface is relevant to custom lab assistants.

- **[Cursor](https://www.cursor.com/)** — AI coding IDE
  - *(2023, [adjacent])* IDE-oriented coding agent (not strictly a CLI) frequently mentioned as a compatible host for skill packs and MCP workflows. Included as adjacent coding-agent infrastructure rather than as a research-agent benchmark target.

## Skills, Workflow Packs, and Reusable Procedures

- **[Anthropic Agent Skills and Claude Code skills](https://code.claude.com/docs/en/skills)** — Anthropic docs
  - *(2025, [CLI-native])* Defines skills as progressively loaded folders with `SKILL.md`, scripts, resources, and optional dynamic context. This is the native packaging pattern behind many Claude Code research workflows.

- **[OpenAI Codex Skills and plugins](https://developers.openai.com/codex/skills)** — OpenAI Developers docs
  - *(2026, [CLI-native])* Documents Codex skills, progressive disclosure, skill locations, and plugin packaging that can bundle skills, app mappings, and MCP config. Useful for making research procedures portable across local, IDE, and cloud Codex contexts.

- **[AI-Research-SKILLs](https://github.com/Orchestra-Research/AI-Research-SKILLs)** — research skill library
  - *(2026, [CLI-native])* Broad skill library for AI research and engineering, spanning ideation, literature, model work, evaluation, MLOps, agents, RAG, and paper writing. It is designed for Claude Code, Codex, Gemini-style agents, and related hosts, and includes meta-patterns for evolving skills.

- **[academic-research-skills](https://github.com/Imbad0202/academic-research-skills)** — Claude Code academic workflow pack
  - *(2026, [CLI-native])* Claude Code skill suite for academic research, writing, review, revision, finalization, and response-to-reviewer artifacts. It emphasizes AI as copilot, pipeline artifacts, integrity reports, reviewer simulation, and reproducibility checks.

- **[claude-code-my-workflow](https://github.com/pedrohcgs/claude-code-my-workflow)** — academic Claude Code workflow
  - *(2026, [CLI-native])* Personal but detailed Claude Code setup for academic work, including papers, slides, data analysis, replication packages, preregistration, review, and referee responses. Its "contractor mode," persistent memory, and adversarial QA loops are useful patterns to borrow.

- **[claude-scholar](https://github.com/Galaxy-Dawn/claude-scholar)** — research assistant configuration
  - *(2026, [CLI-native])* Semi-automated research assistant for CS/AI researchers across literature, coding, experiments, reports, writing, rebuttal, and knowledge management. It combines skills, commands, agents, rules, hooks, Zotero integration, and optional Obsidian workflows while keeping human decisions central.

- **[W&B Skills](https://github.com/wandb/skills)** — experiment-tracking skill library
  - *(2026, [CLI-native])* Installable skills for Claude Code, Codex, and related agents to work with W&B experiments, traces, evals, and reports. They encode common workflows such as model training, run comparison, trace analysis, failure-mode analysis, and report generation.

- **[scientific-agent-skills](https://github.com/K-Dense-AI/scientific-agent-skills)** — scientific skill library
  - *(2026, [CLI-compatible])* Agent Skills catalog across biology, chemistry, medicine, ML, materials, physics, engineering, data analysis, and scientific communication. It broadens the skill-library pattern beyond AI/ML, with explicit compatibility claims for Cursor, Claude Code, and Codex.

- **[ai-skill-scholar](https://github.com/dsebastien/ai-skill-scholar)** — scholarly search skill pack
  - *(2026, [CLI-compatible])* Three skills for scholarly search, citation analysis, and literature review using OpenAlex. The two-pass literature-review orchestrator and persistent session state make it a compact literature layer for coding agents.

- **[ML Experiment Tracking Setup skill](https://mcpmarket.com/tools/skills/ml-experiment-tracking-setup-9)** — tracking boilerplate skill
  - *(2026, [CLI-compatible])* Skill listing for setting up MLflow or W&B experiment-tracking scaffolds before agent-driven iteration. It is useful as a practical prompt/template idea, but independent adoption and maintenance should be verified.

## Literature Discovery and Evidence Grounding

- **[paper-search-mcp](https://github.com/openags/paper-search-mcp)** — paper-search MCP server, CLI, and Claude Code skill
  - *(2026, [CLI-native])* Searches and downloads papers from sources such as arXiv, PubMed, and bioRxiv, and ships both MCP tools and a Claude Code skill. Best used as a discovery layer; novelty judgment and paper-ranking discipline still need separate review.

- **PaperQA2** [![arXiv](https://img.shields.io/badge/arXiv-2409.13740-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2409.13740)
  - *(2024, [CLI-compatible])* Scientific RAG system for answering questions over papers, text, Office files, and code with cited evidence. A coding agent can call it as a literature QA backend for related work, contradiction checks, paper writing, and rebuttal evidence.
  - Code: [Future-House/paper-qa](https://github.com/future-house/paper-qa)

- **[GPT Researcher](https://github.com/assafelovic/gpt-researcher)** — cited report-generation agent
  - *(2024, [CLI-compatible])* Produces long-form research reports over web and local sources with planning, crawling, source tracking, aggregation, memory/context, export, MCP support, and Claude Skill installation. It can feed background sections and briefs, but scholarly claims still need verification.

- **[Zotero MCP / ZotPilot](https://github.com/54yyyu/zotero-mcp)** — local literature-library integrations
  - *(2025, [CLI-compatible])* Zotero MCP exposes a Zotero library, citations, summaries, PDFs, and annotations through MCP; ZotPilot extends the pattern with semantic search and literature-review drafting over local Zotero data. Strong for grounding agents in a curated library rather than repeated ad hoc web search.
  - Related: [ZotPilot forum thread](https://forums.zotero.org/discussion/130483/zotpilot-mcp-server-for-semantic-search-classification-and-literature-review-drafting-from-your-z)

- **[semantic-scholar-mcp](https://github.com/akapet00/semantic-scholar-mcp)** — Semantic Scholar MCP server
  - *(2026, [CLI-compatible])* Lightweight MCP server for searching and analyzing papers through the Semantic Scholar API, with Claude Code setup commands. Useful for citation and related-work checks, but unofficial and small.

- **[arxiv-mcp-server](https://github.com/blazickjp/arxiv-mcp-server)** — arXiv MCP server
  - *(2025, [CLI-compatible])* Lets assistants search, download, store, and analyze arXiv papers through MCP. It includes security guidance about adversarial paper text and prompt injection, a key concern for literature-connected agents.

- **OpenScholar** [![arXiv](https://img.shields.io/badge/arXiv-2411.14199-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2411.14199)
  - *(2024, [adjacent])* Retrieval-augmented scholarly assistant over a large open-access paper corpus, with ScholarQABench-style evaluation for expert scientific questions. It is a canonical grounding layer, but not a coding-agent workflow by itself.
  - Code: [akariasai/openscholar](https://github.com/akariasai/openscholar)

- **STORM: Synthesis of Topic Outlines through Retrieval and Multi-perspective Question Asking** [![arXiv](https://img.shields.io/badge/arXiv-2402.14207-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2402.14207)
  - *(2024, [adjacent])* Generates long-form, grounded articles by discovering perspectives, simulating writer–expert conversations, organizing notes into an outline, and drafting from retrieved sources. Co-STORM extends this with collaborative discourse; the pattern is useful for prewriting and related-work maps, not final scholarship.
  - Code: [stanford-oval/storm](https://github.com/stanford-oval/storm)

- **[Gemini Deep Research Agent](https://ai.google.dev/gemini-api/docs/interactions/deep-research)** — asynchronous research-synthesis API
  - *(2026, [adjacent])* API-level deep-research agent for planning, executing, and synthesizing multi-step research tasks with background execution, planning visualization, MCP, and document input. Closer to research-synthesis than experiment execution; useful as a productized async research pattern.

## Lab Integrations, Notebooks, Experiment Tracking, and Memory

- **[Codex as MCP server with Agents SDK](https://developers.openai.com/codex/guides/agents-sdk)** — OpenAI Developers docs
  - *(2026, [CLI-native])* Exposes Codex through an MCP server with tools such as `codex` and `codex-reply`, enabling orchestrators to delegate coding subproblems to Codex while preserving reviewable traces. Useful for multi-agent research systems that want Codex as a specialized coding worker.

- **[W&B MCP Server](https://docs.wandb.ai/platform/mcp-server)** — experiment-tracking MCP server
  - *(2026, [CLI-compatible])* Lets agents query W&B runs, metrics, experiments, Weave traces, reports, project metadata, and W&B documentation. It has explicit Claude Code and Codex setup paths and is strongest when a lab already logs experiments carefully.
  - Code: [wandb/wandb-mcp-server](https://github.com/wandb/wandb-mcp-server)

- **[MLflow MCP Server and Claude Code tracing](https://mlflow.org/docs/latest/genai/mcp/)** — tracing and experiment-observability integration
  - *(2026, [CLI-compatible])* Exposes MLflow traces and experiment metadata to coding assistants, and supports tracing Claude Code sessions, tool calls, token use, latency, context changes, and evaluation scores. The MCP server is marked experimental, so treat it as promising infrastructure rather than settled standard.
  - Related: [MLflow Claude Code tracing blog](https://mlflow.org/blog/mlflow-claude-code/)

- **[Jupyter MCP Server](https://github.com/datalayer/jupyter-mcp-server)** — notebook and kernel MCP server
  - *(2026, [CLI-compatible])* Gives agents live notebook and kernel control: list kernels, read/edit cells, execute cells, and run code directly. Useful for notebook-heavy research, but should be paired with restart/run-all and raw-data immutability rules.

- **[jupyterlab-collab-mcp](https://github.com/ianhi/jupyterlab-collab-mcp)** — JupyterLab collaboration MCP server
  - *(2026, [CLI-compatible])* MCP server for reading, editing, executing, and coordinating notebook changes from a coding agent connected to a live JupyterLab session. Useful notebook infrastructure that still needs reproducibility discipline (restart/run-all, raw-data immutability).

- **[Notebook Intelligence](https://github.com/notebook-intelligence/notebook-intelligence)** — JupyterLab AI-assistant framework
  - *(2026, [CLI-compatible])* Separate JupyterLab extension/framework that brings Claude Code-style chat, autocomplete, and tool integrations into the notebook interface. Complements MCP-based notebook control.

- **[Letta Code memory system](https://docs.letta.com/letta-code/memory/)** — memory-first coding-agent docs
  - *(2025, [CLI-compatible])* Persistent coding-agent memory with git-backed MemFS, memory self-editing, prior Claude/Codex session ingestion, reflection/dreaming subagents, and skill learning. It addresses cross-session continuity, but persistent memory needs auditing for stale assumptions.

- **[Obsidian Memory / Obsidian MCP-style project memory](https://mcpmarket.com/tools/skills/obsidian-memory-system)** — markdown memory pattern
  - *(2026, [CLI-compatible])* Uses Obsidian vaults and Markdown files for project spaces, goals, daily logs, decisions, long-term knowledge, and semantic search. Useful for long-lived research projects, but stale or contradictory notes need explicit audits.

- **[Model Context Protocol](https://modelcontextprotocol.io/docs/getting-started/intro)** — protocol standard
  - *(2024, [adjacent])* Open standard for connecting AI apps to external data sources, tools, and workflows through clients and servers. For research agents, MCP is the glue for papers, Zotero, W&B, MLflow, notebooks, databases, and custom lab tools.

- **[AgentRxiv](https://agentrxiv.github.io/)** — shared preprint memory for agents
  - *(2025, [adjacent])* Shared preprint-server concept for autonomous research agents, letting future agents retrieve and build on prior agent-generated work instead of rediscovering it. It is a useful long-term memory pattern, with quality-control and contamination risks.

## Autonomous Execution Loops

Long-running loops with persistent state, queues, sandboxes, retries, logs, and experiment execution. For host-level capabilities (Codex cloud, Letta memory) see the relevant sections above; for end-to-end discovery systems see [End-to-End Research and Hypothesis Systems](#end-to-end-research-and-hypothesis-systems).

- **ARIS: Autonomous Research via Adversarial Multi-Agent Collaboration** [![arXiv](https://img.shields.io/badge/arXiv-2605.03042-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2605.03042)
  - *(2026, [CLI-native])* Claude Code/Codex-facing sleep-time research harness with Markdown skills for idea discovery, experiment bridging, auto-review, paper writing, rebuttal, persistent Research Wiki memory, and cross-model reviewer separation. Its strongest mechanism is evidence control: result-to-claim mapping, claim audits, proof checks, deterministic figures, trace saving, and visual PDF inspection.
  - Code: [wanshuiyin/Auto-claude-code-research-in-sleep](https://github.com/wanshuiyin/Auto-claude-code-research-in-sleep)

- **The Agentic Researcher: A Practical Guide to AI-Assisted Research in Mathematics and Machine Learning** [![arXiv](https://img.shields.io/badge/arXiv-2603.15914-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2603.15914)
  - *(2026, [CLI-compatible])* Practical framework for running CLI coding agents such as Claude Code, Codex CLI, OpenCode, and Gemini CLI inside sandboxed research environments. It emphasizes research plans, filesystem isolation, GPU/Slurm/Apptainer support, metric discipline, and recording everything.
  - Code: [ZIB-IOL/The-Agentic-Researcher](https://github.com/ZIB-IOL/The-Agentic-Researcher)

- **[karpathy/autoresearch](https://github.com/karpathy/autoresearch)** — minimal overnight ML loop
  - *(2025, [CLI-compatible])* Prototype loop where an agent reads a high-level `program.md`, edits code, trains a small model under a budget, checks validation bits-per-byte, and keeps or discards changes. It is narrow, but it cleanly illustrates bounded autonomous experiment search.

- **[tinyKaggleClaw](https://github.com/lhwcv/tinyKaggleClaw)** — local multi-agent ML runtime
  - *(2026, [CLI-compatible])* Local-first runtime for Kaggle-style and ML research tasks using a leader, researcher, trainer, tmux, runtime board, inboxes, training queue, and file-backed state. It is an MVP but gives a concrete pattern for coordinating long-running experiment work.

## End-to-End Research and Hypothesis Systems

Research-program orchestration: hypothesis generation, ranking, evolution, experiment tree search, and full discovery pipelines. Distinct from manuscript-focused systems (see next section) and from execution loops above.

- **[AutoResearchClaw](https://github.com/aiming-lab/AutoResearchClaw)** — CLI-compatible autonomous research system
  - *(2026, [CLI-compatible])* Claims topic-to-paper autonomous research with literature search, sandbox experiments, statistical analysis, citation verification, peer review, and LaTeX output across Claude Code, Codex CLI, Gemini CLI, and other hosts. Treat as worth inspecting but in need of independent validation.

- **DeepScientist** [![arXiv](https://img.shields.io/badge/arXiv-2509.26603-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2509.26603)
  - *(2025, [CLI-compatible])* Frames autonomous scientific discovery as long-horizon, goal-oriented search with findings memory, research maps, experiment rounds, and optimization over candidate ideas. The repo ships built-in runners for Codex, Claude Code, Kimi Code, and OpenCode.
  - Code: [ResearAI/DeepScientist](https://github.com/ResearAI/DeepScientist)

- **PARNESS: A Paper Harness for End-to-End Automated Scientific Research with Dynamic Workflows, Full-Text Indexing, and Cross-Run Knowledge Accumulation** [![arXiv](https://img.shields.io/badge/arXiv-2605.05258-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2605.05258)
  - *(2026, [CLI-compatible])* Paper harness with dynamic workflow orchestration, full-PDF/code indexing, persistent knowledge graphs, scenario-typed retrieval, and coding-agent integration. Relevant as a more formal alternative to ad hoc skill folders.

- **Towards an AI co-scientist** [![arXiv](https://img.shields.io/badge/arXiv-2502.18864-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2502.18864)
  - *(2025, [adjacent])* Google Research multi-agent system for generating, debating, ranking, evolving, and meta-reviewing scientific hypotheses, with biomedical validation examples. Its generation–reflection–ranking–evolution loop is directly reusable as a Claude/Codex planning architecture.
  - Blog: [Google Research write-up](https://research.google/blog/accelerating-scientific-breakthroughs-with-an-ai-co-scientist/)

- **AlphaEvolve** [![arXiv](https://img.shields.io/badge/arXiv-2506.13131-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2506.13131)
  - *(2025, [adjacent])* Google DeepMind system that evolves code-based algorithms using LLM proposals, automated evaluators, and an evolutionary database. It is most relevant where research hypotheses can be expressed as executable code with reliable objective metrics.
  - Blog: [Google DeepMind write-up](https://deepmind.google/blog/alphaevolve-a-gemini-powered-coding-agent-for-designing-advanced-algorithms/)

- **[Agent Laboratory](https://github.com/SamuelSchmidgall/AgentLaboratory)** — end-to-end research assistant
  - *(2025, [adjacent])* Research-assistant workflow that starts from a human-provided idea and moves through literature review, experimentation, and report writing. It integrates arXiv, Hugging Face, Python, and LaTeX, with copilot mode for human feedback.

- **The AI Scientist: Towards Fully Automated Open-Ended Scientific Discovery** [![arXiv](https://img.shields.io/badge/arXiv-2408.06292-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2408.06292)
  - *(2024, [adjacent])* Canonical full-loop AI-scientist system for idea generation, novelty checks, experiment execution, visualization, paper writing, and automated review within constrained templates. It is influential, but its own write-ups flag issues such as incorrect implementations, unfair comparisons, visual errors, and code-execution safety.
  - Code: [SakanaAI/AI-Scientist](https://github.com/sakanaai/ai-scientist)

- **[The AI Scientist-v2](https://github.com/sakanaai/ai-scientist-v2)** — agentic-tree-search research system
  - *(2025, [adjacent])* Extends AI Scientist toward less template-bound ML research using progressive agentic tree search, an experiment-manager agent, analysis, manuscript writing, and figure feedback. It is a useful design reference for experiment-tree exploration, but still requires careful sandboxing and human oversight.

- **NanoResearch: Co-Evolving Skills, Memory, and Policy for Personalized Research Automation** [![arXiv](https://img.shields.io/badge/arXiv-2605.10813-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2605.10813)
  - *(2026, [adjacent])* Three-stage research framework (ideation/planning → experimental validation → writing/review) whose distinguishing mechanism is tri-level co-evolution: a skill bank distills recurring operations into reusable procedural rules, a memory module maintains user- and project-bound records that ground planning, and label-free policy learning (SDPO) converts free-form feedback into persistent planner updates. Useful as a personalization reference and a cross-cycle self-evolution alternative to episode-style memory in EvoScientist-class systems.
  - Code: [OpenRaiser/NanoResearch](https://github.com/OpenRaiser/NanoResearch)

- **[FARS: Fully Automated Research System](https://analemma.ai/blog/introducing-fars/)** — autonomous-research project write-up
  - *(2026, [adjacent])* Describes a scaled AI-research pipeline with ideation, planning, experiment, and writing agents, shared filesystem memory, open-access literature, GitLab, model endpoints, and GPU clusters. It is useful for infrastructure patterns, but its claims need independent verification.

## Manuscript, Figure, Reproduction, and Paper-to-Agent Systems

Downstream artifact systems: writing, illustration, paper-to-code reproduction, and paper-to-agent conversion. For the upstream discovery loops that feed these, see [End-to-End Research and Hypothesis Systems](#end-to-end-research-and-hypothesis-systems).

- **PaperOrchestra: A Multi-Agent Framework for Automated AI Research Paper Writing** [![arXiv](https://img.shields.io/badge/arXiv-2604.05018-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2604.05018)
  - *(2026, [CLI-compatible])* Multi-agent paper-writing pipeline that converts research notes, logs, figure observations, and templates into LaTeX through Outline, Plotting, Literature Review, Section Writing, and Content Refinement roles. The repo packages prompts, schemas, halt rules, local helpers, hardening scripts, and agent-log aggregation for coding-agent hosts.
  - Code: [Ar9av/PaperOrchestra](https://github.com/Ar9av/PaperOrchestra)

- **Paper2Agent: Reimagining Research Papers As Interactive and Reliable AI Agents** [![arXiv](https://img.shields.io/badge/arXiv-2509.06917-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2509.06917)
  - *(2025, [CLI-compatible])* Converts papers and codebases into interactive agents by constructing a paper-specific MCP server and validating behavior with generated tests. Useful as a pattern for making methods, analyses, and figures queryable by downstream coding agents.
  - Code: [jmiao24/Paper2Agent](https://github.com/jmiao24/Paper2Agent)

- **Autonomous LLM-driven research from data to human-verifiable research papers** [![arXiv](https://img.shields.io/badge/arXiv-2404.17605-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2404.17605)
  - *(2024, [adjacent])* data-to-paper system for generating transparent, backward-traceable scientific manuscripts from raw data. Its key mechanism is programmatic traceability from reported numbers to analysis code, with review/rewind/replay and human oversight.
  - Code: [Technion-Kishony-lab/data-to-paper](https://github.com/Technion-Kishony-lab/data-to-paper)

- **PaperBanana: Automating Academic Illustration for AI Scientists** [![arXiv](https://img.shields.io/badge/arXiv-2601.23265-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2601.23265)
  - *(2026, [adjacent])* Agentic academic-illustration system for methodology diagrams and some statistical plots. It orchestrates Retriever, Planner, Stylist, Visualizer, and Critic agents, with PaperBananaBench for diagram tasks.
  - Code: [dwzhu-pku/PaperBanana](https://github.com/dwzhu-pku/PaperBanana)

- **[PaperCoder / Paper2Code](https://github.com/going-doer/paper2code)** — paper-to-code system
  - *(2025, [adjacent])* Multi-agent pipeline for converting a research paper into a code repository through planning, architecture/dependency extraction, and modular implementation. It targets a common coding-agent use case: faithful reproduction from paper text.

## Review and Rebuttal Systems

Tools, simulations, and position papers about peer review, reviewer agents, rebuttal generation, and venue-specific guidance.

- **Paper2Rebuttal / RebuttalAgent** [![arXiv](https://img.shields.io/badge/arXiv-2601.14171-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2601.14171)
  - *(2026, [adjacent])* Rebuttal-specific system that parses papers and reviews, extracts atomic concerns, retrieves evidence, plans response strategy, checks consistency and commitments, incorporates author feedback, and drafts formal rebuttals. It is the closest adjacent system to a dedicated Claude/Codex rebuttal skill.
  - Code: [AutoLab-SAI-SJTU/Paper2Rebuttal](https://github.com/AutoLab-SAI-SJTU/Paper2Rebuttal)

- **[Stanford Agentic Reviewer](https://paperreview.ai/tech-overview)** — AI paper-review system
  - *(2025, [adjacent])* Source-grounded review workflow that parses PDFs, retrieves recent arXiv literature, and gives feedback on originality, importance, claim support, soundness, clarity, community value, and contextualization. Useful for private pre-review, not a substitute for artifact-aware peer review.

- **[CSPaper / CSPR](https://cspaper.org/)** — AI-assisted CS paper-review tool
  - *(2025, [adjacent])* Public peer-review tool and demo material focused on rapid CS paper feedback, correctness, and code-validity signals. Include as a peer-review-specific direction, but verify technical depth and deployment claims before depending on it.
  - Paper: [ACL Anthology demo PDF](https://aclanthology.org/2025.inlg-demos.2.pdf)

- **Stop Automating Peer Review Without Rigorous Evaluation** [![arXiv](https://img.shields.io/badge/arXiv-2605.03202-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2605.03202)
  - *(2026, [adjacent])* Position paper arguing against deploying AI reviewers without stronger evaluation, diversity, gaming resistance, and policy controls. Important cautionary reading for anyone wiring Claude Code or Codex into review workflows.

- **AgentReview: Exploring Peer Review Dynamics with LLM Agents** [![arXiv](https://img.shields.io/badge/arXiv-2406.12708-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2406.12708)
  - *(2024, [adjacent])* Simulates peer review with reviewer, author, and area-chair agents, including review, rebuttal, meta-review, and decision interactions. Useful for studying process dynamics and bias, not for validating real expert judgment.
  - Code: [ahren09/agentreview](https://github.com/ahren09/agentreview)

- **[Can large language models provide useful feedback on research papers?](https://github.com/Weixin-Liang/LLM-scientific-feedback)** — empirical feedback study
  - *(2023, [adjacent])* GPT-4 paper-feedback study comparing generated comments with human reviewer feedback on Nature-family and ICLR papers. Useful evidence for draft feedback, but overlap with human comments is not the same as scientific correctness.

- **LLM-REVal** [![arXiv](https://img.shields.io/badge/arXiv-2510.12367-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2510.12367)
  - *(2025, [adjacent])* Studies whether LLMs can serve as reliable peer-review evaluators, including bias toward LLM-generated work and misalignment with human judgments. Use as a caution before relying on agentic reviewers or LLM judges.

- **Author-in-the-Loop Response Generation and Evaluation** [![arXiv](https://img.shields.io/badge/arXiv-2602.11173-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2602.11173)
  - *(2026, [adjacent])* Formalizes review-response generation with author input and introduces resources for response generation, revision alignment, and response evaluation. Provides evaluation framing for future CLI-native rebuttal skills.

- **Defend: Automated Rebuttals for Peer Review with Minimal Author Guidance** [![arXiv](https://img.shields.io/badge/arXiv-2603.27360-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2603.27360)
  - *(2026, [adjacent])* Studies automated rebuttal generation strategies and finds one-shot responses weak on factual correctness and targeted refutation. Supports decomposed, concern-by-concern, author-in-loop rebuttal workflows.

- **[ICML 2026 Peer Review FAQ](https://icml.cc/Conferences/2026/PeerReviewFAQ)** — venue guidance
  - *(2026, [adjacent])* Venue-specific author-response constraints and best practices, including response limits and guidance to focus on factual errors and specific reviewer questions. Rebuttal agents should embed current venue rules rather than draft generic responses.

## Benchmarks and Research Arenas

- **[ResearchArena: How Far Are We From True Auto Research?](https://youarespecialtome.github.io/ResearchArena/index.html)** — CLI-agent research arena
  - *(2026, [CLI-native])* Evaluates off-the-shelf CLI agents including Claude Code, Codex, and Kimi Code across ideation, experiments, paper writing, self-review, code-aware review, and integrity checks. Its main value is direct evidence that current CLI agents still struggle with experimental rigor, significance, fake references, and result/claim mismatches.
  - Code: [YouAreSpecialToMe/ResearchArena](https://github.com/YouAreSpecialToMe/ResearchArena) / [cxcscmu/ResearchArena](https://github.com/cxcscmu/ResearchArena)

- **PaperBench: Evaluating AI's Ability to Replicate AI Research** [![arXiv](https://img.shields.io/badge/arXiv-2504.01848-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2504.01848)
  - *(2025, [adjacent])* Tests whether agents can reproduce 20 ICML 2024 Spotlight/Oral papers from scratch using thousands of author-informed rubric items. Its rollout/reproduction/grading separation is a strong pattern for preventing self-reported success from counting as replication.
  - Code: [OpenAI PaperBench project](https://github.com/openai/frontier-evals/tree/main/project/paperbench)

- **MLAgentBench: Evaluating Language Agents on Machine Learning Experimentation** [![arXiv](https://img.shields.io/badge/arXiv-2310.03302-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2310.03302)
  - *(2023, [adjacent])* Benchmarks agents on iterative ML experimentation tasks where they read/write files, run code, inspect outputs, and improve models. It is an early reference for traceable, sandboxed ML-agent evaluation.
  - Code: [snap-stanford/MLAgentBench](https://github.com/snap-stanford/mlagentbench)

- **[MLE-bench](https://github.com/openai/mle-bench)** — Kaggle-style ML engineering benchmark
  - *(2024, [adjacent])* Evaluates agents on 75 Kaggle competitions requiring data handling, model training, experiments, prediction submission, and objective scoring. It measures practical ML engineering, not scientific novelty, but is useful for testing code-and-experiment loops.

- **[ScienceAgentBench](https://github.com/OSU-NLP-Group/ScienceAgentBench)** — data-driven scientific discovery benchmark
  - *(2025, [adjacent])* Evaluates agents on 102 publication-derived scientific tasks across multiple disciplines, requiring executable Python programs and verified splits. It is a strong check on whether agents can perform science-like analysis rather than only generate prose.

- **[MLGym](https://openreview.net/forum?id=ryTr83DxRq)** — AI research gym benchmark
  - *(2025, [adjacent])* Provides open-ended AI research tasks requiring hypotheses, data, implementation, training, analysis, and iteration. Reported findings that agents often tune hyperparameters rather than invent new algorithms make it useful for expectation-setting.

- **[MLRC-Bench](https://github.com/yunx-z/MLRC-Bench)** — ML research competition benchmark
  - *(2025, [adjacent])* NeurIPS 2025 Datasets & Benchmarks entry that evaluates agents on 7 competition-style ML research problems requiring novel ideas and implementations. Closer to research than ordinary coding benchmarks; small task count makes it narrower than broad ML suites.

- **AAAR-1.0: Assessing AI's Potential to Assist Research** [![arXiv](https://img.shields.io/badge/arXiv-2410.22394-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2410.22394)
  - *(2024, [adjacent])* ICML 2025 benchmark for research-oriented competencies such as equation inference, experiment design, weakness identification, and review critique. Useful as a warning that agent-generated experiment plans can be plausible while trivial, infeasible, or off-objective.

- **[AstaBench](https://openreview.net/forum?id=M7TNf5J26u)** — broad scientific-assistance benchmark
  - *(2026, [adjacent])* ICLR 2026 Oral benchmarking agents across 2,400+ scientific research-assistance problems, many domains, production-grade search tools, and many agent classes. Good as a broad yardstick, but scores may not map cleanly to one lab workflow.

- **ResearchBench** [![arXiv](https://img.shields.io/badge/arXiv-2503.21248-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2503.21248)
  - *(2025, [adjacent])* Benchmarks research reasoning around background, inspiration retrieval, hypothesis composition, and ranking across disciplines. It is most relevant before coding, when assessing whether a plan is scientifically meaningful.

- **[ResearcherBench](https://github.com/GAIR-NLP/ResearcherBench)** — frontier research QA benchmark
  - *(2025, [adjacent])* Evaluates deep AI research systems on expert-curated frontier AI research questions with rubrics for factuality, citation behavior, and insight. It probes high-level research support rather than execution.

- **[AutoResearchBench](https://github.com/CherYou/AutoResearchBench)** — autonomous literature-discovery benchmark
  - *(2025, [adjacent])* Tests "Deep Research" paper-finding tasks and "Wide Research" collection tasks over scientific literature. Useful for evaluating the discovery layer behind novelty checks and rebuttal evidence.

- **[ML-Bench](https://ml-bench.github.io/)** — repository-scale ML-code benchmark
  - *(2026, [adjacent])* Evaluates LLMs and agents on repository-scale ML code interpretation and end-to-end execution across thousands of examples. It targets ML repositories rather than generic programming tasks, but benchmark success is not the same as research validity.

- **ResearchArena: Benchmarking LLMs' Ability to Collect and Organize Information as Research Agents** [![arXiv](https://img.shields.io/badge/arXiv-2406.10291-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2406.10291)
  - *(2024, [adjacent])* Separate literature-survey benchmark from the auto-research arena above; evaluates discovery, selection, organization, and mind-map generation over a large offline paper environment. Useful for literature-agent evaluation, not experiment execution.
  - Paper: [ACL Anthology record](https://aclanthology.org/2025.findings-emnlp.303/)

- **PaperWritingBench** [![arXiv](https://img.shields.io/badge/arXiv-2604.05018-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2604.05018)
  - *(2026, [adjacent])* PaperOrchestra's benchmark built from top-tier AI papers for evaluating automated AI research-paper writing. Useful for manuscript-quality assessment, but it does not validate the underlying research claims.

- **GitTaskBench / OpenHands Index** [![arXiv](https://img.shields.io/badge/arXiv-2508.18993-B31B1B?style=flat&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2508.18993)
  - *(2025, [adjacent])* Benchmark family for real Git tasks and coding-agent performance, including OpenHands-style agents. It is not research-specific, but helps evaluate the coding substrate used inside research-agent systems.

## Practitioner Reports, Methodology Essays, and Agent Frameworks

How researchers and engineers actually build, reason about, and discuss these systems. Mixes operational reports with general multi-agent frameworks that show up as research-agent infrastructure.

- **[Using PLANS.md for multi-hour problem solving](https://developers.openai.com/cookbook/articles/codex_exec_plans)** — OpenAI Developers guide
  - *(2026, [CLI-native])* Planning-artifact pattern for structuring multi-hour Codex work with milestones, state preservation, and continuation guidance. Useful for long research tasks, but it provides process structure rather than scientific validity.

- **[Codex use cases](https://developers.openai.com/codex/use-cases)** — OpenAI Developers docs
  - *(2026, [CLI-native])* Official examples of using Codex for evals, dataset analysis, visualizations, and reports. Useful as a baseline for research-repo task design before adding stronger provenance and statistical guardrails.

- **[An Opinionated Guide to Agentic Coding](https://aidanli.dev/writing/articles/agentic-coding)** — practitioner essay
  - *(2026, [CLI-compatible])* AI researcher's practical report on using Claude Code for research, emphasizing that the harness—repo state, tests, commands, iteration loops, and operational setup—is more important than the model alone.

- **[The agentic researcher - building custom, transparent and extensible workflows with Claude & MCP](https://aarontay.substack.com/p/creating-your-own-research-assistant)** — practitioner report
  - *(2026, [CLI-compatible])* Describes a researcher assembling Claude plus local MCP servers for Zotero, research search, OpenAlex, PubMed, and citation workflows. Useful for concrete MCP assembly patterns and prompt-injection cautions.

- **[Claude Code with Jupyter Notebooks](https://www.reviewnb.com/claude-code-with-jupyter-notebooks)** — ReviewNB guidance
  - *(2026, [CLI-compatible])* Practical guidance for connecting Claude Code to Jupyter through MCP and adding notebook-specific `CLAUDE.md` rules. Key advice: use live kernel tools, avoid raw-data mutation, avoid secret leakage, and restart/run-all for reproducibility.

- **[Microsoft AutoGen](https://microsoft.github.io/autogen/stable//index.html)** — multi-agent framework
  - *(2023, [adjacent])* Framework for single- and multi-agent applications with AgentChat, event-driven workflows, MCP workbenches, Docker code execution, and tool orchestration. Useful for custom research-agent prototypes; in maintenance mode at the upstream.

- **[LangGraph STORM Research Assistant](https://github.com/braincrew-lab/STORM-Research-Assistant)** — graph-based research-writing workflow
  - *(2025, [adjacent])* Implements STORM-style perspective discovery, expert interviews, note curation, and article writing using LangGraph. Useful as a transparent graph orchestration example for literature prewriting.

- **[CAMEL](https://github.com/camel-ai/camel)** — multi-agent research framework
  - *(2023, [adjacent])* Framework/community for scalable multi-agent systems, stateful memory, dynamic communication, simulated environments, data generation, and agent-scaling research. Include when building agent-lab simulations, not as a drop-in Claude/Codex workflow.

## Open Problems and Gaps

- **Claim-to-artifact provenance:** Every paper claim should map to citations, code commits, run IDs, dataset versions, metric definitions, statistical tests, figures, and reviewer concerns. ARIS, PaperOrchestra, data-to-paper, W&B, and MLflow cover pieces, but no shared schema dominates.
- **Research-grade experiment design:** Planning agents need auditable experiment cards: hypothesis, dataset, baseline, metric, ablation, seed plan, compute budget, leakage checks, failure criteria, and claim support. Current tools mostly decompose tasks rather than enforce scientific design.
- **Novelty and citation integrity:** Literature agents retrieve and summarize papers, but still miss clusters, hallucinate references, or overstate novelty. Reliable novelty assessment remains a human-led process with agent assistance.
- **Safe autonomous execution:** Long-running agents need sandboxing, permissioning, GPU budgets, scheduler policies, stop conditions, failed-run triage, and protection against evaluation-script tampering. Long-running compute control is still ad hoc.
- **Figure and notebook provenance:** Agents can generate attractive plots and notebook analyses without guaranteeing clean-run reproducibility, correct filtering, confidence intervals, or faithful captions. Figure provenance contracts are still missing.
- **Artifact-aware review and rebuttal:** Most review tools inspect PDFs more deeply than code, logs, seeds, and environment files. Rebuttal agents need concern matrices that connect reviewer issues to evidence, manuscript changes, new experiments, and commitment risk.
- **Durable memory standards:** `CLAUDE.md`, `AGENTS.md`, Research Wikis, Obsidian vaults, trace folders, and experiment trackers all store pieces of state. Labs need interoperable, auditable memory formats with decay, conflict resolution, and provenance.
- **Evaluation beyond benchmark success:** Current benchmarks measure slices: Kaggle performance, paper replication, scientific programming, literature discovery, or generated-paper review. The field still needs human-in-loop, months-long evaluations of collaboration quality, scientific value, and downstream adoption.

## Contributing

Contributions welcome! Open an issue or pull request if you know of a research agent, skill pack, MCP server, benchmark, or methodology essay that belongs here. See [CONTRIBUTING.md](CONTRIBUTING.md) for inclusion criteria, tagging, section placement, and entry format.

- **Tag:** `CLI-native` (ships explicit Claude Code/Codex skills, configs, or workflows), `CLI-compatible` (works from these agents but not designed for them), or `adjacent` (informs research-agent design without being a CLI workflow).
- **Entry format:** name + link + tag + 1–2 sentence mechanism-focused description.

## Citation

If you find this resource useful, please cite it as:

```bibtex
@software{awesome-research-agents,
  title = {{Awesome Research Agents}},
  author = {Liu, Chris Yuhao and others},
  year = {2026},
  url = {https://github.com/chrisliu298/awesome-research-agents},
  version = {v0.1.0}
}
```

## License

The list itself is released under [CC0 1.0](LICENSE). Linked resources retain their own licenses.

---

*Last updated: 2026-05-12.*
