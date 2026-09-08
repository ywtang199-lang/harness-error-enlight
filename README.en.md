# Harness Error Enlight

[简体中文](README.md) | English

A Chinese-first agent skill for risk-aware debugging, root cause analysis, and learning from recurring errors. It helps coding agents decide how much investigation a problem deserves and when verification is sufficient.

## The problem

| Common failure | Intended behavior |
| --- | --- |
| A restart works and the agent declares the bug fixed | Separate recovery, confirmed root cause, and verified prevention |
| A minor issue turns into an architecture project | Judge actual impact and priority before expanding scope |
| A small fix triggers endless regression testing | Use the smallest check that preserves the failure mechanism, satisfy project gates, then stop |

Recording an error does not make immediate remediation mandatory. Deferring work does not make it resolved.

## Install and try

With the skills CLI:

```sh
npx skills add ywtang199-lang/harness-error-enlight
```

The skill instructions are written in Chinese. This guide provides an English entry point; behavior across languages and agent hosts has not been comprehensively evaluated.

In Codex, try:

> Use $harness-error-enlight to investigate this recurring failure. First assess its impact on our current goal. Distinguish temporary recovery from a confirmed root cause, and define the minimum sufficient verification. Respond in English.

For manual installation and updates, see the [installation instructions](README.md#安装与更新). The skill lives at the repository root in [SKILL.md](SKILL.md). It has no runtime dependencies and does not require the referenced upstream skills.

## What it does

- Checks existing project rules and relevant error records before investigating; historical explanations remain hypotheses until verified.
- Separates issue category, actual impact, and current priority, using the project's priority definitions where available.
- Uses first-principles questions: what outcome matters, what evidence could disprove the explanation, and what would the next experiment change?
- Keeps experiments bounded and informative, including justified repeated trials for intermittent failures.
- Triggers focused adversarial review for recurrence, contradictory evidence, high impact, scope expansion, durable rule changes, or an explicit request.
- Preserves required delivery checks and reports remaining uncertainty before stopping.

It guides an agent's decisions. It is not a background service, an enforcement system, or a guarantee against recurrence. It does not grant permission to change data, publish systems, or expand the task.

## Example: a recurring failure

Illustrative example, not a measured result:

> **Recovery:** Restarting restored the current session.
> **Root cause:** Unconfirmed. A cache issue is a hypothesis, not a finding.
> **Verification:** The original failing operation now succeeds. This does not establish durability across sessions.
> **Next action:** If the temporary recovery is acceptable for the current goal, continue that work and retain a recurrence trigger. If the failure returns, capture the relevant state before another restart.

## Fit into an existing harness

| File | Responsibility |
| --- | --- |
| `AGENTS.md` | Short operating constraints |
| Existing project memory | Durable decisions and context |
| Existing error record | Evidence, failed attempts, effective conditions, recurrence |
| `CONTRIBUTING.md` | Contributor procedures and verification requirements |

Reuse the project's existing records. Do not create a parallel knowledge system merely to use this skill.

## Status and feedback

Early release: text checks and limited behavioral exercises have been performed. There is no published comparative benchmark or established claim of time or token savings.

See [behavior cases](references/behavior-cases.md), [contribution guidance](CONTRIBUTING.md), and the [changelog](CHANGELOG.md). Report a sanitized real failure through [GitHub Issues](https://github.com/ywtang199-lang/harness-error-enlight/issues), including the current goal, agent behavior, expected decision, and relevant evidence. Remove secrets and private project data.

## License and attribution

[MIT](LICENSE). Selectively adapted ideas and upstream license notices are documented in [sources](references/sources.md), including Superpowers, WIO, self-improving-skills, and smarter-agent.
