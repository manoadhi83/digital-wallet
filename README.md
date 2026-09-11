# Digital Wallet POC

A Digital Wallet proof-of-concept: wallet balances, deposits, P2P transfers,
transaction history, and — the core differentiator — idempotency and concurrency safety under
retries and simultaneous requests.

Design methodology follows *System Design Interview – An Insider's Guide, Volume 2* (Alex Xu),
Chapter 12: Digital Wallet, adapted and scoped for this project.

## Status

Work in progress — see the design doc and implementation roadmap for scope, tech stack, and
timeline.

## Tech Stack (V1)

- Spring Boot (monolith), embedded Tomcat
- MySQL (InnoDB)
- Pessimistic row-level locking for concurrency safety
- Idempotency via unique DB constraint
- Spring Security + JWT
- Docker + docker-compose

## Development Workflow

`main` is protected — all changes go through a feature branch and a pull request:

1. `git checkout -b feature/<short-description>`
2. Make changes, commit, `git push -u origin feature/<short-description>`
3. Open a PR into `main` on GitHub
4. Merge once required checks pass (squash merge preferred, for a clean history)
