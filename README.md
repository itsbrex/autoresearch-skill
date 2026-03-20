# Autoresearch Skill

> Fork of [olelehmann100kMRR/autoresearch-skill](https://github.com/olelehmann100kMRR/autoresearch-skill)

A Claude Code skill that autonomously optimizes any other skill by running it repeatedly, scoring outputs against binary evals, mutating the prompt, and keeping improvements. Based on Andrej Karpathy's autoresearch methodology.

## How it works

1. **Baseline** — Run the target skill as-is and score it against binary yes/no eval criteria
2. **Mutate** — Make one targeted change to the skill prompt based on failure analysis
3. **Test** — Re-run the skill and score it again
4. **Keep or discard** — If the score improved, keep the mutation. Otherwise revert.
5. **Repeat** — Loop autonomously until the score ceiling is hit or you stop it

## Outputs

- An improved `SKILL.md` saved back to the original location
- `results.tsv` — score log for every experiment
- `changelog.md` — detailed mutation log
- `dashboard.html` — live browser dashboard that auto-refreshes

## Usage

Trigger with prompts like:
- "optimize this skill"
- "run autoresearch on [skill]"
- "eval my skill"
- "make this skill better"

See [autoresearch/SKILL.md](autoresearch/SKILL.md) for the full skill definition and [autoresearch/references/eval-guide.md](autoresearch/references/eval-guide.md) for how to write good evals.

## Directory Structure

```
autoresearch/
├── SKILL.md              # Skill metadata + instructions
└── references/
    └── eval-guide.md     # How to write good binary evals
```

This follows the [Agent Skills specification](https://agentskills.io/specification).
