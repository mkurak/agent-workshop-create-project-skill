# ⚠️ DEPRECATED — this package moved

> **This repository is no longer maintained.** The `/create-new-project` skill has been moved **into each team that needs it** as of 2026-04-17 (AgentTeamLand Karar #9).

## Why?

The skill is always team-locked in practice — it calls agents from a specific team, it scaffolds a specific stack. Keeping it as a "global" package created the illusion that it was universal, which it was not. Treating scaffolders the way npm treats `create-react-app` / `create-next-app` / `create-vite` (team-scoped, delivered via the team itself) is the correct model.

## What replaced it

The `/create-new-project` skill now lives inside individual teams that choose to expose one. For the .NET + Flutter + React stack, it lives in:

👉 **[agentteamland/software-project-team](https://github.com/agentteamland/software-project-team)** — `/skills/create-new-project/`

Install that team in your project and the skill comes along automatically:

```bash
/team install software-project-team
/create-new-project YourProjectName   # team-scoped scaffolder
```

## Creating your own team scaffolder

If you're building a new team and want to expose `/create-new-project`, follow the [scaffolder spec](https://github.com/agentteamland/core/blob/main/docs/scaffolder-spec.md) in core.

## For full background

See the `brand-identity-and-cli-launch` brainstorm, Karar #9 — the rationale and migration plan are documented there.

## Is this repo going away?

No. It's kept for historical reference. The git history documents the skill's evolution, which is still useful context for anyone building their own scaffolder. But it's not wired into `install.sh` anymore and won't receive updates.
