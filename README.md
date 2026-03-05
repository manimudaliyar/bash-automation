# bash-automation

![Shell](https://img.shields.io/badge/Shell-Bash-4EAA25?logo=gnubash) ![Linux](https://img.shields.io/badge/OS-Linux-FCC624?logo=linux) ![License](https://img.shields.io/badge/License-MIT-green)

> A lightweight Linux system health monitoring toolkit — modular Bash scripts for disk usage tracking and service availability checks, built for ops workflows and CI/CD integration.

---

## Technologies Used

Bash · Linux · systemd · cron-compatible · Exit-code driven (CI/CD ready)

---

## Scripts

### 1. `disk_monitor.sh` — Disk Usage Monitor

Checks disk usage for the root `/` directory and exits non-zero if a configured threshold is exceeded. Appends a timestamped status entry to a log file on every run.

**Usage**

```bash
chmod +x disk_monitor.sh
./disk_monitor.sh
```

**Exit Codes**

| Code | Meaning |
|---|---|
| `0` | Disk usage is within the safe threshold |
| `1` | Disk usage has exceeded the configured threshold |

---

### 2. `service_health_check.sh` — Systemd Service Health Check

Checks whether one or more systemd services are active. Accepts multiple service names as arguments and exits non-zero if any service is found inactive.

**Usage**

```bash
chmod +x service_health_check.sh
./service_health_check.sh docker ssh
```

**Exit Codes**

| Code | Meaning |
|---|---|
| `0` | All specified services are active |
| `1` | One or more services are inactive |

---

## Design Decisions

- **Exit-code driven** — scripts integrate cleanly into CI/CD pipelines, cron jobs, and monitoring systems without modification
- **Modular structure** — each script is single-responsibility; easy to chain or extend
- **Log appending** — disk monitor persists history for trend analysis without overwriting previous entries

---

## Future Enhancements

- [ ] Memory and CPU utilization monitors
- [ ] Alert integration (email / Slack webhook on threshold breach)
- [ ] Centralised log aggregation
- [ ] Cron setup guide for automated scheduling
- [ ] Combined health report script (disk + services in one run)

---

## Author

**Manibharati Mudaliyar**  
[LinkedIn](https://linkedin.com/in/mmudaliyar) · [GitHub](https://github.com/manimudaliyar)
