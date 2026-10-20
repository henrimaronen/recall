# Recall

Recall turns my Apple Books highlights into a personal archive.

![Recall architecture as a transit-line map: Apple Books highlights are emailed to an inbound email webhook, a Go pipeline parses and saves them into PostgreSQL, and from there the line branches to a Python MCP server for AI clients and a TanStack Start web app for reading and curating.](docs/architecture.svg)

## Why I built it

I like to keep my reading sessions active by highlighting the parts that catch my eye. The Apple Books app doesn't offer an easy way to export these highlights, so I needed to find a workaround. Recall is that workaround: all my highlights land in one database, where I can use them in whatever way I find useful.

## Tech stack

| Part       | Stack                                                                    |
| ---------- | ------------------------------------------------------------------------ |
| Pipeline   | Go, `net/http`, golang-migrate, Docker                                   |
| Database   | PostgreSQL, plain SQL migrations shared across services                  |
| MCP server | Python, official MCP SDK, stdio transport                                |
| Web app    | TypeScript, TanStack Start, node-postgres with raw SQL                   |
| Quality    | pytest, Vitest integration tests on real Postgres, Playwright E2E, Biome |


## Source

This repository is an overview only. The source code is private.