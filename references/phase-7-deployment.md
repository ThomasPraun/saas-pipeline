# Phase 7: Deployment

## Contents
- [Objective](#objective)
- [Skills](#skills)
- [Workflow](#workflow) (Steps 1-3)
- [Exit Criteria](#exit-criteria)

## Objective

Containerize the application and prepare for production deployment.

## Skills

| Order | Skill | Purpose |
|-------|-------|---------|
| 1 | docker-expert | Dockerfile, docker-compose, optimization, security |

## Workflow

### Step 1: Gather Context

Before delegating, collect:
- Stack from CLAUDE.md (determines base images, build steps)
- Architecture from Phase 4 (`docs/architecture/`)
- Environment variables and external service dependencies

### Step 2: Containerize

Delegate to `docker-expert` with full application context. The skill handles Dockerfiles, docker-compose, and health checks.

### Step 3: Verify

```
docker compose build
docker compose up -d
docker compose ps       # all containers healthy
docker compose logs     # no startup errors
```

Run test suite against containerized environment.

Save deployment docs to `docs/deployment/docker-setup.md`.

## Exit Criteria

- [ ] Dockerfile(s) with multi-stage builds
- [ ] docker-compose.yml with all services
- [ ] Health checks configured
- [ ] `docker compose build` succeeds
- [ ] `docker compose up` starts all services healthy
- [ ] Application works correctly in containers
- [ ] Deployment docs created

## Notes

- For mobile apps (Flutter mobile, React Native), adapt to CI/CD + app store deployment instead of Docker
