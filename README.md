# Digital Wallet POC

A production-grade Digital Wallet proof-of-concept: wallet balances, deposits, P2P transfers,
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
