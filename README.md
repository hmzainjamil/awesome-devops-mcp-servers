# Awesome DevOps MCP Servers

This repository is a reference-list project for discovering DevOps-related Model Context Protocol servers. A catalog entry is a pointer to a separate project, not evidence that its server is safe, maintained, compatible, or suitable for production.

## Review a server before use

An MCP server may access infrastructure, source code, credentials, or deployment systems. Before connecting one:

- Verify the upstream repository, maintainer, license, and current release.
- Review its available tools, permissions, dependencies, and network behavior.
- Use a disposable project and least-privilege credentials for evaluation.
- Confirm side effects before connecting it to production systems.

The recursive tree on `docs/mcp-list-scope-and-verification` was checked on 2026-10-02. It contains this README, a contribution guide, a security policy, a license, and a funding file; no `.github/workflows/` or `docs/README.md` was found. No server implementation or integration test was verified.

See [CONTRIBUTING.md](CONTRIBUTING.md) for entry requirements, [SECURITY.md](SECURITY.md) for connection review guidance, [LICENSE](LICENSE) for repository licensing, and [CONTENT_REVIEW.md](CONTENT_REVIEW.md) for the removed claims and evidence scope. The repository license does not change the terms of linked servers.
