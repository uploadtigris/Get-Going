# Go Learning Projects

Five projects for building practical Go skills alongside RHCSA prep.
Thematically focused on infrastructure, systems, and security.

---

## Suggested Order

`sysmon` → `logwatch` → `httpcheck` → `portscanner` → `sshaudit`

Starting with `sysmon` for pure Linux + Go fundamentals, build toward concurrency and I/O with
`logwatch` and `httpcheck`, then lean into the security angle with `portscanner` and `sshaudit`.

---

## Projects

### 1. `sysmon` — System Resource Monitor

Poll `/proc` for CPU, memory, disk, and network stats and print a live-updating dashboard to
the terminal.

**Skills:**
- Reading and parsing Linux kernel interfaces (`/proc`)
- Goroutines for concurrent polling
- Terminal output formatting

**Why it matters:** Direct overlap with what Prometheus/Node Exporter does under the hood.
Understanding my own homelab stack better.

---

### 2. `logwatch` — Log File Tailer & Alerter

Watch a log file for pattern matches using `fsnotify` and print alerts when a regex hits.

**Skills:**
- File I/O and `fsnotify`
- Goroutines and channels
- Regex matching

**Why it matters:** Point it at my actual Nginx access logs or `/var/log/audit/audit.log`
in the homelab.

---

### 3. `httpcheck` — HTTP Endpoint Health Checker

Read a list of URLs from a config file (YAML or TOML), hit them on a schedule, and report
status and latency. Alert when a service goes down.

**Skills:**
- HTTP client usage
- Concurrency with goroutines
- Config file parsing
- Timeouts and context cancellation

**Why it matters:** The building blocks of any monitoring tool. Complements the
Prometheus/Grafana setup conceptually.

---

### 4. `portscanner` — TCP Port Scanner

Dial TCP connections concurrently across a port range on a target host and report which
are open.

**Skills:**
- Goroutines and `sync.WaitGroup`
- Context with deadlines
- Raw network/socket programming

**Why it matters:** Understand what `nmap` is actually doing at the socket level with strong connection with my Security+ background and the security engineering path.

---

### 5. `sshaudit` — SSH Login Log Parser

Parse `/var/log/secure` (or `journalctl -u sshd`) for failed and successful SSH login
events, aggregate by IP, and output a ranked report.

**Skills:**
- Text parsing and regex
- Structs, maps, and sorting
- File and pipe input

**Why it matters:** This one can graduate into an actual tool in your workflow — wire the
output into `sysadmin_handbook` incident documentation.

---

## Go Skills Coverage

| Project | Goroutines | File I/O | Networking | Parsing | HTTP |
|---|---|---|---|---|---|
| `sysmon` | ✓ | ✓ | | | |
| `logwatch` | ✓ | ✓ | | ✓ | |
| `httpcheck` | ✓ | | | | ✓ |
| `portscanner` | ✓ | | ✓ | | |
| `sshaudit` | | ✓ | | ✓ | |

---

## Resources

- [gobyexample.com](https://gobyexample.com) — best quick reference for syntax and patterns
- [pkg.go.dev](https://pkg.go.dev) — standard library docs
- *The Go Programming Language* by Donovan & Kernighan — the definitive book
