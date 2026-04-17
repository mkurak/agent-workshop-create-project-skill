# 🚀 Create New Project Skill

Scaffold a complete production-ready project with a single command. In 5 minutes, get the same mature infrastructure that would take weeks to build manually.

## Installation

```bash
/team install https://github.com/agentteamland/create-project.git
```

> Requires [Agent Team Manager](https://github.com/agentteamland/team-manager) to be installed first.

## Usage

```bash
/create-new-project MyAwesomeApp
```

The skill asks a few key questions, then creates everything:

1. **Project name** — PascalCase (e.g., WalkingForMe, ProductGlitz)
2. **Applications** — Flutter mobile? React web? React SSR?
3. **SaaS?** — Multi-tenant with User + Profile + Tenant, or simple single-tenant
4. **Modules** — File storage, audit trail, soft delete
5. **Port offset** — Avoid conflicts with other projects on the same machine

## What Gets Created

### Always Included (Core Infrastructure)

| Component | Technology |
|-----------|-----------|
| API | .NET 9, Minimal API, Vertical Slice + Clean Arch + Mediator |
| Database | PostgreSQL 17, EF Core 9 |
| Messaging | RabbitMQ 3 (fanout exchanges: logs, emails) |
| Cache | Redis 7 (tokens, cache, locks) |
| Logging | Serilog → RMQ → LogIngest → Elasticsearch 8 + Kibana |
| Email | MailSender (RMQ consumer) → Mailpit (dev SMTP) |
| Auth | JWT HS256 (15min access, 30day refresh), BCrypt |
| Real-time | SignalR WebSocket bridge |
| Scheduler | Worker with Cronos cron jobs |
| Infrastructure | Docker Compose (14+ services), dotnet watch (hot reload) |

### Optionally Included

| Module | What It Adds |
|--------|-------------|
| Flutter | Mobile app skeleton (Riverpod, go_router, Dio, i18n) |
| React (Vite) | Web app skeleton (TypeScript, Tailwind, React Query, Zustand) |
| React (Next.js) | SSR web app with SEO support |
| SaaS | User + Profile + Tenant, multi-tenant data isolation, embed auth |
| File Storage | MinIO (S3-compatible) in dev, IStorageService abstraction |
| Audit Trail | AuditLog table with automatic change tracking |
| Soft Delete | ISoftDeletable + global query filter (default: included) |

### Also Created

- `docker-compose.yml` with 14+ services, health checks, shadow volumes
- `.env` / `.env.example` with all configuration
- `CLAUDE.md` with project documentation
- `.claude/` directory with hooks, rules, coding standards, brainstorm/backlog structure
- `Seeds/seed.sql` with test admin user
- Swagger UI at `/swagger`
- Health endpoint at `/api/health/ping`

## Architecture

```
API (brain) ← Socket (bridge) ← Worker (scheduler)
    ↓                                    
RabbitMQ → LogIngest → Elasticsearch     
         → MailSender → SMTP             
```

All business logic lives in the API. Everything else is a bridge.

## After Creation

The skeleton is ready. Now use the [Software Project Team](https://github.com/agentteamland/software-project-team) agents to build features:

- **API Agent** — add features (Command/Handler/Validator/Endpoint)
- **Flutter Agent** — build mobile screens
- **React Agent** — build web pages
- **Database Agent** — optimize schema and queries
- **And 9 more specialized agents...**

## License

MIT
