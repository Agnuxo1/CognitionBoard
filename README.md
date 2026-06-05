# CognitionBoard

CognitionBoard is a set of 20 domain-expert Markdown skills for LLM agents. It uses a 6x4 board notation so an agent can route a task through specialist skills and record the reasoning path compactly.

| Goal | Link |
|---|---|
| Use the master skill | `skills/MASTER-SKILL.md` |
| Browse all skills | `skills/` |
| Review new-skill contribution plan | `docs/NEW_COGNITIVE_SKILLS.md` |
| Open the ecosystem anchor | https://github.com/Agnuxo1/OpenCLAW-P2P |
| Live P2PCLAW network | https://www.p2pclaw.com |

## What It Is

CognitionBoard helps agents choose a structured reasoning path across science, humanities, applied disciplines, synthesis, and output formatting. A path such as `D5.A1.A2.B6.D6` records:

```text
D5 Master -> A1 Token Compression -> A2 Mathematics -> B6 Economics -> D6 Output
```

The board path becomes a short session memory and makes multi-domain reasoning easier to inspect.

## Board Layout

| Row | Focus | Cells |
|---|---|---|
| A | Core science | Token compression, mathematics, physics, chemistry, biology, computer science |
| B | Humanities | history, philosophy, psychology, linguistics, geography, economics |
| C | Applied disciplines | politics, law, medicine, astronomy, engineering, arts |
| D | Environment, culture, synthesis, routing, output | environment, culture, science synthesis, humanities synthesis, master, output |

Always start at `D5` and end at `D6`.

## Example Paths

| Task | Path | Meaning |
|---|---|---|
| Prove a theorem | `D5.A1.A2.D6` | master, compression, mathematics, output |
| Quantum chemistry | `D5.A1.A2.A3.A4.D3.D6` | math, physics, chemistry, science synthesis |
| French Revolution economics | `D5.A1.B1.B6.D6` | history and economics |
| Climate policy | `D5.A1.D1.C1.D4.D6` | environment, politics, humanities synthesis |
| Bioinformatics pipeline | `D5.A1.A5.A6.D3.D6` | biology, computer science, science synthesis |

## Installation

### Option 1: VS Code Extension

Install from the VS Code Marketplace:

```text
ext install agnuxo1.cognitive-skills-engine
```

### Option 2: Git Clone

```bash
git clone https://github.com/Agnuxo1/CognitionBoard.git
cd CognitionBoard/skills
```

Then load `MASTER-SKILL.md` into your agent context.

### Option 3: Copy-Paste

1. Open `skills/MASTER-SKILL.md`.
2. Copy it into your agent's system prompt or project instructions.
3. Ask the agent to route tasks using CognitionBoard paths.

## Contributing Skills

Issue #1 tracks three proposed additions:

- Neuroscientist,
- Anthropologist,
- Roboticist.

See [docs/NEW_COGNITIVE_SKILLS.md](docs/NEW_COGNITIVE_SKILLS.md) for suggested board placement, metadata, tests, and acceptance criteria.

## Ecosystem

| Project | Role | Link |
|---|---|---|
| OpenCLAW-P2P | Canonical protocol, papers, policies, and research dossier | https://github.com/Agnuxo1/OpenCLAW-P2P |
| P2PCLAW | Live decentralized research network | https://www.p2pclaw.com |
| CAJAL | Local scientific paper generation | https://github.com/Agnuxo1/CAJAL |
| BenchClaw | Agent benchmarking | https://github.com/Agnuxo1/benchclaw |
| EnigmAgent | Local encrypted vault for agents | https://github.com/Agnuxo1/EnigmAgent |
| PaperClaw | IDE research-paper publishing client | https://github.com/Agnuxo1/paperclaw-extension |

## Citation

```bibtex
@software{cognitionboard_2026,
  author = {Angulo de Lafuente, Francisco},
  title = {CognitionBoard: Board-Routed Cognitive Skills for LLM Agents},
  year = {2026},
  url = {https://github.com/Agnuxo1/CognitionBoard},
  note = {Part of the P2PCLAW decentralized research network}
}
```

## License

Apache 2.0. See `LICENSE`.

Created by Francisco Angulo de Lafuente. ORCID: https://orcid.org/0009-0001-1634-7063
