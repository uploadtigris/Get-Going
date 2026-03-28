Here's a clean markdown version:

---

**Go + Docker DevOps Learning Path**

**Go**
- Complete [tour.golang.org](https://go.dev/tour) (~4 hours)
- Focus on: structs, interfaces, goroutines, channels, error handling
- Key stdlib packages: `os`, `os/exec`, `net/http`, `flag`/`cobra`, `encoding/json`, `log/slog`
- Read [Effective Go](https://go.dev/doc/effective_go) after writing ~500 lines
- Resources: [Gophercises](https://gophercises.com) (free, project-based), *Let's Go* by Alex Edwards

**Docker**
- Learn: images, containers, volumes, networks
- Core commands: `build`, `run`, `exec`, `ps`, `logs`
- Dockerfile keywords: `FROM`, `COPY`, `RUN`, `CMD`, `ENTRYPOINT`, `ENV`, `EXPOSE`
- Learn multi-stage builds (essential for small Go images)
- Learn `docker compose` for multi-container local dev
- Resources: [Docker Get Started](https://docs.docker.com/get-started/), *Docker Deep Dive* by Nigel Poulton

**Build Loop**
- Write Go tool → `go build` → `docker build` → `docker run` → iterate

**Starter Projects**
- URL health checker
- Log parser (stdin/file filtering)
- Config linter (YAML/JSON validation)
- Prometheus metrics exporter

**Timeline**
- Week 1: Go tour + first CLI tool
- Week 2: Error handling, structs, interfaces, stdlib I/O
- Week 3: Docker basics + containerize your tools
- Week 4: Multi-stage builds, docker compose, goroutines
- Weeks 5–6: Build a real end-to-end tool