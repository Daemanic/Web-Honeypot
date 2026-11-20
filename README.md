# ST5041CMD [Course]
> The Internet and Web Technologies.

---

## [~] Web Honeypot with Attack Dashboard

A fake system that looks real and valuable, but exists only to be attacked.

| Course | ST5041CMD - The Internet and Web Technologies |
|---|---|
| Purpose | Capture, classify and visualise web attacks against an decoy site. |

---

## [~] Overview

A `honeypot` is a decoy that no real user has a reason to visit, a every request to it is suspicious.

**This project has two parts:**

* Decoy website: a fake site with tempting targets (fake admin logs, fake `/.env`, fake search box). It records everything sent to it and never executes attacker input.
* Attack dashboard: a private, secured analyst page that turns that logs into charts, tables and reports.

**Goals:**

* Detect and classify common web attacks (SQLi, XSS, path traversal, scanning, brute force).
* Learn how real attacks look at the HTTP level.
* Measure detection quality (detection rate, false positives).
* Apply secure web development to the project itself.

---

## [~] How It Works

```
Attacker / bot
      ↓
Decoy web app (Flask)         → fake pages, fake login, catch-all route
      ↓
Logger + Classifier           → tags: sqli, xss, traversal, scanner, brute_force
      ↓
Enrichment                    → GeoIP country, tool guess from User-Agent
      ↓
Database (SQLite)             → events, ips, credentials_tried, rules
      ↓
Dashboard (private)           → login + MFA, charts, live feed, export
```

---
