# ⚠️ DEPRECATED — `create-project` moved into individual teams

> **This repository is no longer maintained.** As of 2026-04-17 (AgentTeamLand Karar #9), the `/create-new-project` skill has been moved **into each team that needs it** rather than living as a standalone package. Treating scaffolders the way npm treats `create-react-app` / `create-next-app` (team-scoped, delivered via the team itself) turned out to be the correct model — the skill is always team-locked in practice anyway.

The repo is kept for historical reference. The git history documents the skill's evolution, which remains useful context for anyone building their own scaffolder. But it's not wired into `install.sh` anymore and won't receive updates.

## What replaced it

For the .NET + Flutter + React stack, the skill now lives in **[`agentteamland/software-project-team`](https://github.com/agentteamland/software-project-team)** under `skills/create-new-project/`. Install that team in your project and the skill comes along automatically:

```bash
atl install software-project-team
/create-new-project YourProjectName   # team-scoped scaffolder
```

## 📚 Documentation

Full docs live at **[agentteamland.github.io/docs](https://agentteamland.github.io/docs/)**.

Most relevant sections:

- [`software-project-team`](https://agentteamland.github.io/docs/teams/software-project-team) — the team that ships the replacement `/create-new-project` skill
- [Scaffolder spec](https://agentteamland.github.io/docs/authoring/scaffolder-spec) — guide for building your own team-scoped `/create-new-project` skill
- [`atl install`](https://agentteamland.github.io/docs/cli/install) — `atl install software-project-team` (the legacy `/team install` was retired in `team-manager@2.0.0`)

## License

MIT.
