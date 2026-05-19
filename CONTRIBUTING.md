# Contributing

Contributions welcome! Open an issue or PR to add or correct entries.

## Inclusion criteria

A resource qualifies if it falls into one of the following families AND is reasonably well-documented (a public repo, paper, or vendor doc page — not just a tweet):

1. **CLI-native skill libraries / workflow packs** — skills, slash commands, hooks, subagent definitions, or `CLAUDE.md` / `AGENTS.md` configurations explicitly designed for Claude Code, Codex CLI, or a comparable coding-agent CLI to perform research-related tasks.
2. **Research-oriented MCP servers** — MCP servers that expose paper search, scientific databases, experiment trackers, lab notebooks, or similar research-flavored tools to coding agents.
3. **Sleep-time / autonomous research loops** — long-running agent loops that plan, run, evaluate, and revise experiments or research artifacts, especially when the design is adapted to or hostable by Claude Code / Codex.
4. **Multi-agent paper-writing or end-to-end research systems** — pipelines that go from idea or data to a draft paper through staged agent roles. Include even when not CLI-native if the architecture is influential.
5. **AI co-scientist / autonomous-scientist systems** — hypothesis generation, ranking, debate, and evolution systems aimed at scientific discovery.
6. **Literature-grounded research agents** — RAG systems specifically targeting scientific papers, citation grounding, novelty checking, or literature QA.
7. **Coding-agent CLIs themselves** — only the CLIs that show up in actual research-agent workflows in the list (Claude Code, Codex, Aider, Gemini CLI, OpenHands, Goose, etc.).
8. **Research arenas and benchmarks** — benchmarks that test research-relevant capabilities: experiment design, reproducing papers, ML engineering, peer review, claim verification, and similar.
9. **Practitioner essays and methodology reports** — reports from researchers about how they actually use these systems, when they include load-bearing operational lessons (not vibes-only blog posts).

### What does NOT qualify

- **Generic coding-agent tooling** without a research-workflow connection. A great VS Code extension for refactoring is not in scope.
- **Generic LLM-based research surveys** that do not produce a system, skill pack, or benchmark.
- **Twitter threads with no underlying repo or paper.** A thread that documents a clear, reproducible workflow can be cited inline as supporting context for an existing entry, but does not warrant its own bullet.
- **Vaporware.** If the repo has no usable code and the paper has no public artifact, wait until something ships.
- **Forks without distinct contribution.** If a fork only changes branding or trivial wiring, link to the upstream instead.

## Tagging

Tag each entry with one of:

- **CLI-native** — explicitly ships skills, prompts, or configs for Claude Code, Codex, or a comparable CLI.
- **CLI-compatible** — works well as a tool/library called from a CLI agent, but not designed for one.
- **adjacent** — important for understanding the field but not a CLI workflow itself (most autonomous-scientist systems and benchmarks).

When in doubt, prefer the more conservative tag.

## Entry format

Entries are single-line bullets. Lead with what it is and the mechanism. Be terse — no filler ("a great resource", "the leading", "comprehensive").

For papers with arXiv:

```
- [Title](https://arxiv.org/abs/XXXX.YYYYY) *(Year, [Tag])* — One-sentence mechanism-focused description. [![Code](https://img.shields.io/badge/Code-181717?style=flat&logo=github&logoColor=white)](https://github.com/org/repo)
```

For repos / tools / skill packs:

```
- [Name](https://github.com/org/repo) *(Year, [Tag])* — One-sentence description.
```

For docs / blog posts:

```
- [Title](url) *(Year, [Tag])* — One-sentence description.
```

Drop the `Code` shield when there is no separate code repo. Append other shield badges sparingly, only when load-bearing.

## Section placement

The README's entry-bearing sections:

- Coding-Agent Substrates and Hosts
- Skills, Workflow Packs, and Reusable Procedures
- Literature Discovery and Evidence Grounding
- Lab Integrations, Notebooks, Experiment Tracking, and Memory
- Autonomous Execution Loops
- End-to-End Research and Hypothesis Systems
- Manuscript, Figure, Reproduction, and Paper-to-Agent Systems
- Review and Rebuttal Systems
- Benchmarks and Research Arenas
- Practitioner Reports, Methodology Essays, and Agent Frameworks

A resource may legitimately fit two sections (e.g., ARIS as both a skill pack and an autonomous loop). Pick the one closest to its primary contribution.

Within each section, entries are ordered CLI-native first, then CLI-compatible, then adjacent.

## Stars and maturity figures

GitHub stars and fork counts rot fast. Only include them when they are load-bearing for understanding scale (e.g., "44k+ stars" for Aider). For most entries, omit.

## Verification

Before submitting:

- Confirm the link resolves and the project is still maintained (or note "archived" / "unmaintained" if not).
- Confirm the entry is not already in the list (search by name AND by URL — different repos sometimes use the same name).
- For arXiv papers, confirm the arXiv ID matches the title — easy to swap two digits and end up linking the wrong paper.
