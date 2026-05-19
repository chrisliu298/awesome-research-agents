# 🔍 Awesome Research Agents

<p align="center">
  <a href="https://awesome.re"><img src="https://img.shields.io/badge/Awesome-%F0%9F%94%8D_Research_Agents-000000?style=for-the-badge&labelColor=000000" alt="Awesome Research Agents"></a>
  <a href="https://github.com/chrisliu298/awesome-research-agents/stargazers"><img src="https://img.shields.io/github/stars/chrisliu298/awesome-research-agents?style=for-the-badge&logo=github&logoColor=white&label=Stars&labelColor=000000&color=000000" alt="GitHub Stars"></a>
  <a href="https://github.com/chrisliu298/awesome-research-agents/network/members"><img src="https://img.shields.io/github/forks/chrisliu298/awesome-research-agents?style=for-the-badge&logo=github&logoColor=white&label=Forks&labelColor=000000&color=000000" alt="GitHub Forks"></a>
  <a href="https://github.com/chrisliu298/awesome-research-agents/commits"><img src="https://img.shields.io/github/last-commit/chrisliu298/awesome-research-agents?style=for-the-badge&logo=github&logoColor=white&label=Last%20Commit&labelColor=000000&color=000000" alt="Last Commit"></a>
</p>

Curated resources for building, evaluating, and stress-testing research agents around Claude Code, OpenAI Codex CLI, and adjacent coding-agent CLIs — across AI/ML research workflows: literature, hypothesis design, implementation, experiments, analysis, writing, review, rebuttal, and project memory.

**New here?** Read [Start Here](#start-here). **Shipping a workflow?** Skip to [Coding-Agent Substrates and Hosts](#coding-agent-substrates-and-hosts) and [Skills, Workflow Packs, and Reusable Procedures](#skills-workflow-packs-and-reusable-procedures).

> If you maintain a research-agent project that should be on this list, or spot a mistake, broken link, or stale entry, please open an issue or pull request.

## Contents

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

## Tagging

Tags are conservative and used for within-section ordering (CLI-native → CLI-compatible → adjacent):

- **CLI-native** — ships explicit Claude Code/Codex skills, configs, docs, or workflows.
- **CLI-compatible** — usable from these CLIs but not primarily built for them.
- **adjacent** — informs research-agent design without being a CLI workflow.

## Start Here

1. **[Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview)** — core Claude-native substrate: repo editing, shell, skills, hooks, subagents, memory, MCP.
2. **[OpenAI Codex CLI / Codex](https://github.com/openai/codex)** — OpenAI-native substrate: local CLI, `AGENTS.md`, skills, MCP, cloud/background tasks, parallel work.
3. **[AI-Research-SKILLs](https://github.com/Orchestra-Research/AI-Research-SKILLs)** — broadest reusable research-skill library before writing your own.
4. **[ARIS](https://arxiv.org/abs/2605.03042)** — strongest Claude/Codex-facing autonomous research loop with claim-audit patterns.
5. **[PaperOrchestra](https://arxiv.org/abs/2604.05018)** — main paper-writing and figure-generation reference.
6. **[PaperQA2](https://arxiv.org/abs/2409.13740)** — literature-grounded retrieval instead of model memory for citations.
7. **[ResearchArena (CLI-agent arena)](https://youarespecialtome.github.io/ResearchArena/index.html)** — calibrates expectations on direct CLI research-agent evaluation.
8. **[Stop Automating Peer Review Without Rigorous Evaluation](https://arxiv.org/abs/2605.03202)** — read before deploying review/rebuttal agents.
9. **[AI for Auto-Research: Roadmap & User Guide](https://arxiv.org/abs/2605.18661)** — comprehensive lifecycle survey of the whole field as one map.

## Research Stage Map

| Stage | Useful entries |
|---|---|
| Idea & literature | AI-Research-SKILLs, ARIS, PaperQA2, LitLLM, OpenScholar, OpenNovelty, STORM, ResearchAgent, ai-skill-scholar, paper-search-mcp |
| Experiment design | ARIS, The Agentic Researcher, Agent Laboratory, AI co-scientist, EvoScientist, AAAR-1.0 |
| Coding | Claude Code, OpenAI Codex CLI, Aider, Gemini CLI, OpenHands, PaperCoder / Paper2Code |
| Execution | ARIS, W&B MCP Server, MLflow MCP Server, MLE-bench, MLAgentBench, CORE-Bench, RE-Bench, tinyKaggleClaw |
| Analysis | Jupyter MCP Server, W&B Skills, MLflow MCP Server, data-to-paper, PaperOrchestra |
| Writing | PaperOrchestra, Agent Laboratory, The AI Scientist, data-to-paper, GPT Researcher |
| Peer review | ResearchArena, Stanford Agentic Reviewer, AgentReview, The AI Scientist, LLM-REVal, Re2 |
| Rebuttal | Paper2Rebuttal, DRPG, ARIS, claude-code-my-workflow, ICML 2026 Peer Review FAQ |
| Project memory | Claude Code, OpenAI Codex CLI, Letta Code, Obsidian Memory, Zotero MCP / ZotPilot, PARNESS, AgentRxiv |

## Coding-Agent Substrates and Hosts

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview) *(2025, [CLI-native])* — Terminal-native coding agent that reads repos, edits files, runs commands, and composes with `CLAUDE.md`, skills, subagents, hooks, permissions, MCP, and SDK workflows.
- [OpenAI Codex CLI / Codex](https://github.com/openai/codex) *(2025, [CLI-native])* — Local and cloud/background coding agent with `AGENTS.md`, skills, MCP, subagents, worktrees, and parallel task support for implementation, evals, analysis, and reports.
- [OpenAI Codex cloud/background tasks](https://developers.openai.com/codex/app) *(2026, [CLI-native])* — Codex web/cloud mode for delegating tasks into isolated GitHub-connected environments; maps to ablations, eval additions, and report-generation threads.
- [Aider](https://github.com/aider-ai/aider) *(2023, [CLI-compatible])* — Terminal pair-programming agent with repo maps, file editing, lint/test loops, broad model support, and automatic git commits.
- [Gemini CLI](https://github.com/google-gemini/gemini-cli) *(2025, [CLI-compatible])* — Open-source terminal agent with file tools, shell, web fetch, Google Search grounding, MCP, and `GEMINI.md` customization.
- [OpenHands](https://github.com/OpenHands/OpenHands) *(2024, [CLI-compatible])* — Model-agnostic software-agent platform with SDK, CLI, local GUI, cloud/enterprise modes, and benchmark infrastructure.
- [goose](https://github.com/aaif-goose/goose) *(2025, [CLI-compatible])* — Provider-agnostic agent for code, workflows, research, writing, automation, and data analysis with MCP extensions, recipes, subagents, and CLI/desktop/API modes.
- [Cursor](https://www.cursor.com/) *(2023, [adjacent])* — IDE-oriented coding agent frequently mentioned as a compatible host for skill packs and MCP workflows.

## Skills, Workflow Packs, and Reusable Procedures

- [Anthropic Agent Skills and Claude Code skills](https://code.claude.com/docs/en/skills) *(2025, [CLI-native])* — Skills as progressively loaded folders with `SKILL.md`, scripts, resources, and optional dynamic context; native packaging pattern.
- [OpenAI Codex Skills and plugins](https://developers.openai.com/codex/skills) *(2026, [CLI-native])* — Codex skills with progressive disclosure, skill locations, and plugin packaging for skills, app mappings, and MCP config.
- [AI-Research-SKILLs](https://github.com/Orchestra-Research/AI-Research-SKILLs) *(2026, [CLI-native])* — Broad skill library across ideation, literature, model work, evaluation, MLOps, agents, RAG, and paper writing for Claude Code, Codex, and Gemini-style hosts.
- [academic-research-skills](https://github.com/Imbad0202/academic-research-skills) *(2026, [CLI-native])* — Claude Code skill suite for academic research, writing, review, revision, finalization, response-to-reviewer artifacts, integrity reports, reviewer simulation, and reproducibility checks.
- [claude-code-my-workflow](https://github.com/pedrohcgs/claude-code-my-workflow) *(2026, [CLI-native])* — Personal Claude Code setup for papers, slides, data analysis, replication packages, preregistration, review, and referee responses; notable "contractor mode" and adversarial QA loops.
- [claude-scholar](https://github.com/Galaxy-Dawn/claude-scholar) *(2026, [CLI-native])* — Semi-automated research assistant for CS/AI across literature, coding, experiments, reports, writing, rebuttal, and knowledge management; skills + commands + agents + rules + hooks + Zotero + optional Obsidian.
- [W&B Skills](https://github.com/wandb/skills) *(2026, [CLI-native])* — Installable Claude Code / Codex skills for W&B experiments, traces, evals, and reports (training, run comparison, failure-mode analysis, report generation).
- [Organon](https://github.com/krmdel/organon) *(2026, [CLI-native])* — Claude Code scientific OS covering literature search, hypothesis testing, data analysis, manuscript drafting, scheduled jobs, and science communication, with verification gates that block fabricated citations and unsupported claims.
- [MedSci Skills](https://github.com/Aperivue/medsci-skills) *(2026, [CLI-native])* — Medical-science Claude Code skill suite (~39 skills) across topic discovery, literature search, study design, statistics, figures, writing, compliance, peer review, revision, and presentations with PubMed/Semantic Scholar/CrossRef-verified citations.
- [Claude Code for an Academic Researcher](https://github.com/flonat/claude-research) *(2026, [CLI-native])* — Full Claude Code infrastructure for academics with 48 skills, 6 agents, 9 hooks, rules, context libraries, LaTeX, bibliography tooling, Notion integration, and reviewer roles (domain reviewer, paper critic, peer reviewer, referee).
- [scientific-agent-skills](https://github.com/K-Dense-AI/scientific-agent-skills) *(2026, [CLI-compatible])* — Agent Skills catalog across biology, chemistry, medicine, ML, materials, physics, engineering, data analysis, and scientific communication with Cursor / Claude Code / Codex compatibility.
- [ai-skill-scholar](https://github.com/dsebastien/ai-skill-scholar) *(2026, [CLI-compatible])* — Three skills for scholarly search, citation analysis, and literature review via OpenAlex; two-pass orchestrator with persistent session state.
- [EvoSkills](https://github.com/EvoScientist/EvoSkills) *(2026, [CLI-compatible])* — Installable research-skill library for ideation, paper planning, experiment pipelines, writing, review, rebuttal, memory, paper navigation, and surveys across Claude Code, Codex, Gemini CLI, Cursor, OpenCode, and DeepAgents.
- [ML Experiment Tracking Setup skill](https://mcpmarket.com/tools/skills/ml-experiment-tracking-setup-9) *(2026, [CLI-compatible])* — Skill for scaffolding MLflow or W&B experiment-tracking before agent-driven iteration; verify adoption before depending on it.

## Literature Discovery and Evidence Grounding

- [paper-search-mcp](https://github.com/openags/paper-search-mcp) *(2026, [CLI-native])* — Searches and downloads papers from arXiv, PubMed, bioRxiv via MCP tools and a Claude Code skill; discovery layer only — ranking discipline still needed.
- [LitLLM](https://github.com/LitLLM/LitLLM) *(2025, [CLI-native])* — Literature-review toolkit and Claude Code skill for retrieving, ranking, and synthesizing related work over OpenAlex, Google Scholar, embedding search, and LLM reranking.
- [PaperQA2](https://arxiv.org/abs/2409.13740) *(2024, [CLI-compatible])* — Scientific RAG over papers, text, Office files, and code with cited evidence; callable as a literature-QA backend for related work, contradiction checks, paper writing, and rebuttals. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/future-house/paper-qa)
- [GPT Researcher](https://github.com/assafelovic/gpt-researcher) *(2024, [CLI-compatible])* — Long-form cited research reports over web and local sources with planning, crawling, source tracking, MCP, and Claude Skill install; scholarly claims still need verification.
- [Zotero MCP / ZotPilot](https://github.com/54yyyu/zotero-mcp) *(2025, [CLI-compatible])* — Zotero library, citations, summaries, PDFs, and annotations via MCP; ZotPilot adds semantic search and lit-review drafting over local data.
- [semantic-scholar-mcp](https://github.com/akapet00/semantic-scholar-mcp) *(2026, [CLI-compatible])* — Lightweight MCP server for searching and analyzing papers through the Semantic Scholar API; unofficial and small.
- [arxiv-mcp-server](https://github.com/blazickjp/arxiv-mcp-server) *(2025, [CLI-compatible])* — Search, download, store, and analyze arXiv papers via MCP, with security guidance on adversarial paper text and prompt injection.
- [PubMed MCP Server](https://chat.mcp.so/server/pubmed-mcp-server/cyanheads) *(rolling, [CLI-compatible])* — PubMed / NCBI E-utilities MCP with article search, retrieval, research-plan generation, filtering, citation analysis, metadata visualization, and biomedical research-agent scaffolding.
- [OpenScholar](https://arxiv.org/abs/2411.14199) *(2024, [adjacent])* — Retrieval-augmented scholarly assistant over a large open-access corpus with ScholarQABench-style evaluation; canonical grounding layer, not a CLI workflow. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/akariasai/openscholar)
- [STORM](https://arxiv.org/abs/2402.14207) *(2024, [adjacent])* — Long-form grounded articles via perspective discovery, simulated writer-expert chat, outline organization, and drafting from retrieved sources; Co-STORM adds collaborative discourse. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/stanford-oval/storm)
- [Gemini Deep Research Agent](https://ai.google.dev/gemini-api/docs/interactions/deep-research) *(2026, [adjacent])* — API-level deep-research agent for planning, executing, and synthesizing multi-step research with background execution, planning viz, MCP, and document input.
- [OpenNovelty](https://arxiv.org/abs/2601.01576) *(2026, [adjacent])* — Agentic novelty-assessment pipeline that extracts claims, retrieves prior work, builds a hierarchical taxonomy, compares contributions against full texts, and produces evidence-grounded novelty reports. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/january-blue/OpenNovelty)

## Lab Integrations, Notebooks, Experiment Tracking, and Memory

- [Codex as MCP server with Agents SDK](https://developers.openai.com/codex/guides/agents-sdk) *(2026, [CLI-native])* — Exposes Codex via MCP with `codex` and `codex-reply` tools so orchestrators can delegate coding to Codex while preserving reviewable traces.
- [W&B MCP Server](https://docs.wandb.ai/platform/mcp-server) *(2026, [CLI-compatible])* — Lets agents query W&B runs, metrics, experiments, Weave traces, reports, project metadata, and W&B docs with explicit Claude Code / Codex setup paths. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/wandb/wandb-mcp-server)
- [MLflow MCP Server and Claude Code tracing](https://mlflow.org/docs/latest/genai/mcp/) *(2026, [CLI-compatible])* — Exposes MLflow traces and experiment metadata to coding assistants; supports tracing Claude Code tool calls, tokens, latency, context, and eval scores; experimental.
- [Jupyter MCP Server](https://github.com/datalayer/jupyter-mcp-server) *(2026, [CLI-compatible])* — Live notebook/kernel control (list kernels, read/edit cells, execute); pair with restart/run-all and raw-data immutability rules.
- [jupyterlab-collab-mcp](https://github.com/ianhi/jupyterlab-collab-mcp) *(2026, [CLI-compatible])* — MCP server for reading, editing, executing, and coordinating notebook changes from a coding agent connected to a live JupyterLab session.
- [Notebook Intelligence](https://github.com/notebook-intelligence/notebook-intelligence) *(2026, [CLI-compatible])* — JupyterLab extension bringing Claude Code-style chat, autocomplete, and tool integrations into the notebook UI; complements MCP-based notebook control.
- [Letta Code memory system](https://docs.letta.com/letta-code/memory/) *(2025, [CLI-compatible])* — Persistent coding-agent memory with git-backed MemFS, self-editing memory, prior session ingestion, reflection/dreaming subagents, and skill learning; audit for stale assumptions.
- [Obsidian Memory](https://mcpmarket.com/tools/skills/obsidian-memory-system) *(2026, [CLI-compatible])* — Obsidian vaults and Markdown for project spaces, goals, daily logs, decisions, long-term knowledge, and semantic search; needs stale/conflict audits.
- [Model Context Protocol](https://modelcontextprotocol.io/docs/getting-started/intro) *(2024, [adjacent])* — Open standard for connecting AI apps to external data, tools, and workflows; the glue for papers, Zotero, W&B, MLflow, notebooks, and custom lab tools.
- [AgentRxiv](https://agentrxiv.github.io/) *(2025, [adjacent])* — Shared preprint-server concept for autonomous research agents to retrieve and build on prior agent-generated work; quality-control and contamination risks.

## Autonomous Execution Loops

- [ARIS: Autonomous Research via Adversarial Multi-Agent Collaboration](https://arxiv.org/abs/2605.03042) *(2026, [CLI-native])* — Sleep-time Claude/Codex research harness with skills for idea discovery, experiments, auto-review, paper writing, rebuttal, and a Research Wiki; strongest mechanism is result-to-claim mapping, claim audits, proof checks, deterministic figures, and visual PDF inspection. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/wanshuiyin/Auto-claude-code-research-in-sleep)
- [The Agentic Researcher](https://arxiv.org/abs/2603.15914) *(2026, [CLI-compatible])* — Practical framework for Claude Code, Codex CLI, OpenCode, and Gemini CLI inside sandboxed research environments with research plans, filesystem isolation, GPU/Slurm/Apptainer, and metric discipline. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/ZIB-IOL/The-Agentic-Researcher)
- [karpathy/autoresearch](https://github.com/karpathy/autoresearch) *(2025, [CLI-compatible])* — Minimal overnight ML loop where an agent reads `program.md`, edits code, trains under budget, checks val bits-per-byte, and keeps or discards changes.
- [tinyKaggleClaw](https://github.com/lhwcv/tinyKaggleClaw) *(2026, [CLI-compatible])* — Local-first multi-agent runtime for Kaggle-style ML tasks using leader/researcher/trainer, tmux, runtime board, inboxes, training queue, and file-backed state.

## End-to-End Research and Hypothesis Systems

- [AutoResearchClaw](https://github.com/aiming-lab/AutoResearchClaw) *(2026, [CLI-compatible])* — Claims topic-to-paper autonomous research with literature search, sandbox experiments, statistical analysis, citation verification, peer review, and LaTeX across Claude Code, Codex CLI, Gemini CLI, and other hosts; needs independent validation.
- [DeepScientist](https://arxiv.org/abs/2509.26603) *(2025, [CLI-compatible])* — Frames autonomous discovery as long-horizon goal-oriented search with findings memory, research maps, experiment rounds, and idea optimization; ships built-in runners for Codex, Claude Code, Kimi Code, and OpenCode. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/ResearAI/DeepScientist)
- [PARNESS](https://arxiv.org/abs/2605.05258) *(2026, [CLI-compatible])* — Paper harness with dynamic workflow orchestration, full-PDF/code indexing, persistent knowledge graphs, scenario-typed retrieval, and coding-agent integration.
- [EvoScientist](https://arxiv.org/abs/2603.08127) *(2026, [CLI-compatible])* — Evolving multi-agent AI scientist with Researcher, Engineer, and Evolution Manager agents plus ideation/experimentation memory, CLI/TUI execution, Docker sandboxing, MCP, and skills across a planning-to-verification workflow. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/EvoScientist/EvoScientist)
- [Towards an AI co-scientist](https://arxiv.org/abs/2502.18864) *(2025, [adjacent])* — Google Research multi-agent system for generating, debating, ranking, evolving, and meta-reviewing scientific hypotheses with biomedical validation; the generation–reflection–ranking–evolution loop reuses as a Claude/Codex planning architecture.
- [ResearchAgent](https://arxiv.org/abs/2404.07738) *(2025, [adjacent])* — Iterative research-idea generation over scientific-literature graphs and knowledge stores, with multiple ReviewingAgents evaluating candidate problems, methods, and experiments. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/JinheonBaek/ResearchAgent)
- [Rethinking the AI Scientist: Interactive Multi-Agent Workflows for Scientific Discovery](https://arxiv.org/abs/2601.12542) *(2026, [adjacent])* — Multi-agent scientific-discovery workflow unifying planning, data analysis, literature search, and novelty detection through a persistent world state, with both semi-autonomous and autonomous modes.
- [AlphaEvolve](https://arxiv.org/abs/2506.13131) *(2025, [adjacent])* — DeepMind system evolving code-based algorithms via LLM proposals, automated evaluators, and an evolutionary database; best where hypotheses are executable with reliable objective metrics.
- [Agent Laboratory](https://github.com/SamuelSchmidgall/AgentLaboratory) *(2025, [adjacent])* — Research-assistant workflow from human-provided idea through literature review, experimentation, and report writing with arXiv, HF, Python, LaTeX, and copilot mode.
- [The AI Scientist](https://arxiv.org/abs/2408.06292) *(2024, [adjacent])* — Canonical full-loop AI-scientist for idea generation, novelty checks, experiment execution, visualization, paper writing, and automated review; own write-ups flag incorrect implementations, unfair comparisons, visual errors, and code-execution safety. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/sakanaai/ai-scientist)
- [The AI Scientist-v2](https://github.com/sakanaai/ai-scientist-v2) *(2025, [adjacent])* — Extends AI Scientist toward less template-bound ML research via progressive agentic tree search, an experiment-manager agent, analysis, manuscript writing, and figure feedback.
- [NanoResearch](https://arxiv.org/abs/2605.10813) *(2026, [adjacent])* — Three-stage personalized research framework whose distinguishing mechanism is tri-level co-evolution: skill bank distilling recurring operations, user/project memory grounding planning, and label-free SDPO converting free-form feedback into persistent planner updates. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/OpenRaiser/NanoResearch)
- [FARS: Fully Automated Research System](https://analemma.ai/blog/introducing-fars/) *(2026, [adjacent])* — Scaled AI-research pipeline with ideation, planning, experiment, and writing agents, shared filesystem memory, open-access literature, GitLab, model endpoints, and GPU clusters; claims need independent verification.

## Manuscript, Figure, Reproduction, and Paper-to-Agent Systems

- [PaperOrchestra](https://arxiv.org/abs/2604.05018) *(2026, [CLI-compatible])* — Multi-agent paper-writing pipeline that turns research notes, logs, figure observations, and templates into LaTeX through Outline, Plotting, Literature Review, Section Writing, and Refinement roles, with prompts, schemas, halt rules, and hardening scripts. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/Ar9av/PaperOrchestra)
- [Paper2Agent](https://arxiv.org/abs/2509.06917) *(2025, [CLI-compatible])* — Converts papers and codebases into interactive agents by constructing a paper-specific MCP server validated with generated tests; makes methods, analyses, and figures queryable by downstream coding agents. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/jmiao24/Paper2Agent)
- [data-to-paper](https://arxiv.org/abs/2404.17605) *(2024, [adjacent])* — LLM-driven research from raw data to transparent, backward-traceable manuscripts; key mechanism is programmatic traceability from reported numbers to analysis code with review/rewind/replay and human oversight. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/Technion-Kishony-lab/data-to-paper)
- [PaperBanana](https://arxiv.org/abs/2601.23265) *(2026, [adjacent])* — Agentic academic-illustration system for methodology diagrams orchestrating Retriever, Planner, Stylist, Visualizer, and Critic agents with PaperBananaBench. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/dwzhu-pku/PaperBanana)
- [PaperCoder / Paper2Code](https://github.com/going-doer/paper2code) *(2025, [adjacent])* — Multi-agent pipeline converting a research paper into a code repository through planning, architecture/dependency extraction, and modular implementation.

## Review and Rebuttal Systems

- [Paper2Rebuttal / RebuttalAgent](https://arxiv.org/abs/2601.14171) *(2026, [adjacent])* — Rebuttal-specific system that parses papers and reviews, extracts atomic concerns, retrieves evidence, plans response strategy, checks commitments, incorporates author feedback, and drafts formal rebuttals. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/AutoLab-SAI-SJTU/Paper2Rebuttal)
- [DRPG: Decompose, Retrieve, Plan, Generate for Review-Rebuttal Generation](https://arxiv.org/abs/2601.18081) *(2026, [adjacent])* — Evidence-grounded rebuttal agent with Decomposer, Retriever, Planner, and Executor modules for decomposing reviewer concerns, retrieving paper evidence, planning response strategy, and generating rebuttal text. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/ulab-uiuc/DRPG-RebuttalAgent)
- [Stanford Agentic Reviewer](https://paperreview.ai/tech-overview) *(2025, [adjacent])* — Source-grounded review workflow parsing PDFs and retrieving recent arXiv on originality, importance, claim support, soundness, clarity, community value, and contextualization.
- [CSPaper / CSPR](https://cspaper.org/) *(2025, [adjacent])* — Public peer-review tool focused on rapid CS paper feedback with correctness and code-validity signals; verify technical depth before depending on it.
- [Stop Automating Peer Review Without Rigorous Evaluation](https://arxiv.org/abs/2605.03202) *(2026, [adjacent])* — Position paper against deploying AI reviewers without stronger evaluation, diversity, gaming resistance, and policy controls; required cautionary reading.
- [AgentReview](https://arxiv.org/abs/2406.12708) *(2024, [adjacent])* — Simulates peer review with reviewer, author, and area-chair agents through review, rebuttal, meta-review, and decision; for studying process dynamics and bias, not validating real expert judgment. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/ahren09/agentreview)
- [Can LLMs provide useful feedback on research papers?](https://github.com/Weixin-Liang/LLM-scientific-feedback) *(2023, [adjacent])* — GPT-4 paper-feedback study comparing generated comments with human reviewer feedback on Nature-family and ICLR papers; overlap is not scientific correctness.
- [LLM-REVal](https://arxiv.org/abs/2510.12367) *(2025, [adjacent])* — Studies whether LLMs can serve as reliable peer-review evaluators, including bias toward LLM-generated work and misalignment with human judgments.
- [Author-in-the-Loop Response Generation and Evaluation](https://arxiv.org/abs/2602.11173) *(2026, [adjacent])* — Formalizes review-response generation with author input and introduces resources for response generation, revision alignment, and response evaluation.
- [Defend: Automated Rebuttals with Minimal Author Guidance](https://arxiv.org/abs/2603.27360) *(2026, [adjacent])* — Studies automated rebuttal strategies; finds one-shot responses weak on factual correctness and targeted refutation, supporting decomposed concern-by-concern workflows.
- [ICML 2026 Peer Review FAQ](https://icml.cc/Conferences/2026/PeerReviewFAQ) *(2026, [adjacent])* — Venue-specific author-response constraints and response limits; rebuttal agents should embed current venue rules rather than draft generic responses.

## Benchmarks and Research Arenas

- [ResearchArena: How Far Are We From True Auto Research?](https://youarespecialtome.github.io/ResearchArena/index.html) *(2026, [CLI-native])* — Evaluates Claude Code, Codex, Kimi Code across ideation, experiments, paper writing, self-review, code-aware review, and integrity; direct evidence CLI agents still struggle with experimental rigor, significance, fake references, and result/claim mismatches. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/YouAreSpecialToMe/ResearchArena)
- [PaperBench](https://arxiv.org/abs/2504.01848) *(2025, [adjacent])* — Tests whether agents can reproduce 20 ICML 2024 Spotlight/Oral papers from scratch via thousands of author-informed rubric items; rollout/reproduction/grading separation prevents self-reported success from counting as replication. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/openai/frontier-evals/tree/main/project/paperbench)
- [MLAgentBench](https://arxiv.org/abs/2310.03302) *(2023, [adjacent])* — Benchmarks agents on iterative ML experimentation (read/write files, run code, inspect outputs, improve models); early reference for traceable sandboxed ML-agent evaluation. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/snap-stanford/mlagentbench)
- [MLE-bench](https://github.com/openai/mle-bench) *(2024, [adjacent])* — Evaluates agents on 75 Kaggle competitions requiring data handling, training, experiments, prediction submission, and objective scoring; practical ML engineering, not scientific novelty.
- [ScienceAgentBench](https://github.com/OSU-NLP-Group/ScienceAgentBench) *(2025, [adjacent])* — 102 publication-derived scientific tasks across disciplines requiring executable Python and verified splits; strong check on science-like analysis versus prose generation.
- [MLGym](https://openreview.net/forum?id=ryTr83DxRq) *(2025, [adjacent])* — Open-ended AI research tasks (hypotheses, data, implementation, training, analysis); reported finding that agents often tune hyperparameters rather than invent new algorithms.
- [MLRC-Bench](https://github.com/yunx-z/MLRC-Bench) *(2025, [adjacent])* — NeurIPS 2025 Datasets & Benchmarks entry evaluating agents on 7 competition-style ML research problems requiring novel ideas and implementations.
- [AAAR-1.0](https://arxiv.org/abs/2410.22394) *(2024, [adjacent])* — ICML 2025 benchmark for equation inference, experiment design, weakness identification, and review critique; warning that agent-generated experiment plans can be plausible while trivial or infeasible.
- [AstaBench](https://openreview.net/forum?id=M7TNf5J26u) *(2026, [adjacent])* — ICLR 2026 Oral benchmarking agents across 2,400+ scientific research-assistance problems with production-grade search; broad yardstick that may not map to one lab workflow.
- [ResearchBench](https://arxiv.org/abs/2503.21248) *(2025, [adjacent])* — Benchmarks research reasoning around background, inspiration retrieval, hypothesis composition, and ranking; most relevant pre-coding for assessing scientific meaningfulness of a plan.
- [ResearcherBench](https://github.com/GAIR-NLP/ResearcherBench) *(2025, [adjacent])* — Evaluates deep AI research systems on expert-curated frontier AI research questions with rubrics for factuality, citation, and insight; probes high-level research support rather than execution.
- [AutoResearchBench](https://github.com/CherYou/AutoResearchBench) *(2025, [adjacent])* — Tests "Deep Research" paper-finding and "Wide Research" collection tasks over scientific literature; useful for evaluating the discovery layer behind novelty checks and rebuttal evidence.
- [ML-Bench](https://ml-bench.github.io/) *(2026, [adjacent])* — Evaluates LLMs and agents on repository-scale ML code interpretation and end-to-end execution across thousands of examples.
- [ResearchArena: Benchmarking LLMs as Research Agents](https://arxiv.org/abs/2406.10291) *(2024, [adjacent])* — Separate literature-survey benchmark from the auto-research arena; evaluates discovery, selection, organization, and mind-map generation over a large offline paper environment.
- [PaperWritingBench](https://arxiv.org/abs/2604.05018) *(2026, [adjacent])* — PaperOrchestra's benchmark built from top-tier AI papers for evaluating automated AI research-paper writing; does not validate underlying research claims.
- [CORE-Bench](https://arxiv.org/abs/2409.11363) *(2024, [adjacent])* — Computational-reproducibility benchmark with 270 tasks from 90 scientific papers across CS, social science, and medicine; ships a runnable harness with Docker/Azure execution and trace/logging guidance. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/siegelz/core-bench)
- [RE-Bench](https://arxiv.org/abs/2411.15114) *(2024, [adjacent])* — Seven open-ended ML research-engineering environments with human-expert comparison (71 eight-hour attempts by 61 experts); METR task-standard formatting with Vivaria scaffolding hooks. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/METR/RE-Bench)
- [Re2: Consistency-ensured Dataset for Full-stage Peer Review and Multi-turn Rebuttal](https://arxiv.org/abs/2505.07920) *(2025, [adjacent])* — Dataset covering submissions, reviews, ratings, rebuttals, discussions, score changes, meta-reviews, and decisions for benchmarking review, rebuttal, reviewer-simulation, and author-response agents.
- [SciReplicate-Bench](https://openreview.net/forum?id=8LoPjpvWde) *(2025, [adjacent])* — 100 reproducibility tasks from 36 NLP papers paired with Sci-Reproducer, a dual-agent system coordinating a Paper Agent for understanding and a Code Agent for execution. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/xyzCS/SciReplicate-Bench)
- [InnovatorBench / ResearchGym](https://arxiv.org/abs/2510.27598) *(2025, [adjacent])* — Code-based research-innovation benchmark with ResearchGym environments for data construction/filtering/augmentation, loss design, reward design, and scaffold construction; rich action spaces, long-horizon execution, asynchronous monitoring, and snapshot saving.
- [FIRE-Bench: Full-cycle Insight Rediscovery Evaluation](https://arxiv.org/abs/2602.02905) *(2026, [adjacent])* — Full-cycle research benchmark where agents explore ideas, design and run experiments, implement code, and derive evidence-supported conclusions from verified ML studies.
- [ReplicationBench: Can AI Agents Replicate Astrophysics Research Papers?](https://openreview.net/forum?id=HuxsI5Ecao) *(2026, [adjacent])* — Paper-scale benchmark for AI agents replicating expert-validated astrophysics research tasks with full-paper replication and objective correctness checks.
- [GitTaskBench / OpenHands Index](https://arxiv.org/abs/2508.18993) *(2025, [adjacent])* — Benchmark family for real Git tasks and coding-agent performance including OpenHands-style agents; helps evaluate the coding substrate inside research-agent systems.

## Practitioner Reports, Methodology Essays, and Agent Frameworks

- [Using PLANS.md for multi-hour problem solving](https://developers.openai.com/cookbook/articles/codex_exec_plans) *(2026, [CLI-native])* — Planning-artifact pattern for structuring multi-hour Codex work with milestones, state preservation, and continuation guidance; process structure, not scientific validity.
- [Codex use cases](https://developers.openai.com/codex/use-cases) *(2026, [CLI-native])* — Official Codex examples for evals, dataset analysis, visualizations, and reports; baseline before adding provenance and statistical guardrails.
- [How NVIDIA engineers and researchers build with Codex](https://openai.com/index/nvidia/) *(2026, [CLI-native])* — Official OpenAI case study on NVIDIA research/engineering using Codex for ML workflows: identifying areas, writing experiment scripts, running remote experiments, codebase search, and paper-corpus evidence work.
- [An Opinionated Guide to Agentic Coding](https://aidanli.dev/writing/articles/agentic-coding) *(2026, [CLI-compatible])* — Practitioner essay arguing the harness (repo state, tests, commands, iteration loops, operational setup) matters more than the model alone.
- [The agentic researcher — Claude & MCP](https://aarontay.substack.com/p/creating-your-own-research-assistant) *(2026, [CLI-compatible])* — Researcher assembling Claude plus local MCP servers for Zotero, research search, OpenAlex, PubMed, and citations; concrete MCP assembly with prompt-injection cautions.
- [Claude Code with Jupyter Notebooks](https://www.reviewnb.com/claude-code-with-jupyter-notebooks) *(2026, [CLI-compatible])* — Connecting Claude Code to Jupyter via MCP with notebook `CLAUDE.md` rules: live kernel tools, no raw-data mutation, no secret leakage, restart/run-all for reproducibility.
- [Getting Started with Claude Code: A Researcher's Setup Guide](https://paulgp.substack.com/p/getting-started-with-claude-code) *(2026, [CLI-compatible])* — Practical Claude Code setup for empirical researchers: local research projects, data cleaning, debugging, reformatting, scraping, reproducibility, and collaborative workflows with referees, advisers, and coauthors.
- [Microsoft AutoGen](https://microsoft.github.io/autogen/stable//index.html) *(2023, [adjacent])* — Framework for single- and multi-agent applications with AgentChat, event-driven workflows, MCP workbenches, Docker code execution, and tool orchestration; upstream in maintenance mode.
- [LangGraph STORM Research Assistant](https://github.com/braincrew-lab/STORM-Research-Assistant) *(2025, [adjacent])* — STORM-style perspective discovery, expert interviews, note curation, and article writing in LangGraph; transparent graph orchestration example for prewriting.
- [CAMEL](https://github.com/camel-ai/camel) *(2023, [adjacent])* — Framework for scalable multi-agent systems, stateful memory, dynamic communication, simulated environments, data generation, and agent-scaling research.
- [Agentic AI Scientists Are Not Built For Autonomous Scientific Discovery](https://arxiv.org/abs/2605.08956) *(2026, [adjacent])* — Position paper arguing for machine-readable preregistration, failure logging, diversity tracking, and safeguards before treating agentic AI scientists as autonomous discovery systems.
- [AI for Auto-Research: Roadmap & User Guide](https://arxiv.org/abs/2605.18661) *(2026, [adjacent])* — End-to-end survey across four phases (Creation, Writing, Validation, Dissemination) and eight stages, identifying a stage-dependent boundary between reliable assistance and unreliable autonomy; ships taxonomy, benchmark suite, tool inventory, and practitioner playbook. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/worldbench/awesome-ai-auto-research)

## Open Problems and Gaps

- **Claim-to-artifact provenance** — every paper claim should map to citations, code commits, run IDs, dataset versions, metric definitions, statistical tests, figures, and reviewer concerns; ARIS, PaperOrchestra, data-to-paper, W&B, and MLflow cover pieces, no shared schema dominates.
- **Research-grade experiment design** — planning agents need auditable experiment cards (hypothesis, dataset, baseline, metric, ablation, seed plan, compute budget, leakage checks, failure criteria, claim support); current tools mostly decompose tasks rather than enforce scientific design.
- **Novelty and citation integrity** — literature agents retrieve and summarize but still miss clusters, hallucinate references, or overstate novelty; reliable novelty assessment remains human-led with agent assistance.
- **Safe autonomous execution** — long-running agents need sandboxing, permissioning, GPU budgets, scheduler policies, stop conditions, failed-run triage, and protection against evaluation-script tampering; long-running compute control is still ad hoc.
- **Figure and notebook provenance** — agents generate attractive plots and analyses without guaranteeing clean-run reproducibility, correct filtering, confidence intervals, or faithful captions; figure-provenance contracts are missing.
- **Artifact-aware review and rebuttal** — most review tools inspect PDFs more deeply than code, logs, seeds, and environment files; rebuttal agents need concern matrices linking reviewer issues to evidence, revisions, new experiments, and commitment risk.
- **Durable memory standards** — `CLAUDE.md`, `AGENTS.md`, Research Wikis, Obsidian vaults, trace folders, and experiment trackers all store pieces of state; labs need interoperable, auditable memory formats with decay, conflict resolution, and provenance.
- **Evaluation beyond benchmark success** — current benchmarks measure slices (Kaggle, paper replication, scientific programming, literature discovery, generated-paper review); the field still needs human-in-loop months-long evaluations of collaboration quality, scientific value, and downstream adoption.

## Contributing

Contributions welcome. Open an issue or PR if you know of a research agent, skill pack, MCP server, benchmark, or methodology essay that belongs here. See [CONTRIBUTING.md](CONTRIBUTING.md) for inclusion criteria, tagging, section placement, and entry format.

- **Tag:** `CLI-native`, `CLI-compatible`, or `adjacent` (see [Tagging](#tagging)).
- **Entry format:** `- [Title](url) *(Year, [Tag])* — one-sentence mechanism-focused description.` Append shield badges (e.g. `[![Code](...)]`) for secondary links.

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

*Last updated: 2026-05-19.*
