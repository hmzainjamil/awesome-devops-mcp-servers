# Awesome DevOps MCP Servers

This repository is intended to help discover Model Context Protocol servers related to DevOps. The previous README included unsupported server counts, production-use rankings, install/configuration commands, APIs, performance claims, case studies, test results, and status details. References to `docs/`, a CI workflow directory, and a security policy were not found at the checked paths. These claims have been removed pending evidence.

## Review an MCP server before use

An MCP server can read or change infrastructure, access source code, retrieve secrets, trigger deployments, or send data to an external service. Before connecting one:

- Verify the upstream repository, maintainer, latest release, license, and current compatibility.
- Review server tools and their permission scope.
- Inspect dependency, install, and runtime behavior.
- Test with a disposable project and least-privilege credentials.
- Confirm actions and resource effects before production use.

A directory listing or recommendation does not establish that an MCP server is safe or maintained.

## Contribute entries

The [contribution guide](CONTRIBUTING.md) asks contributors to provide a name, link, language/scope indicators, and description. Add the upstream license, last-checked date, maintained status, and concise evidence for any ranking or production claim.

The list's root [MIT license](LICENSE) applies to this repository's covered material; it does not change terms of linked MCP servers.

See [CONTENT_REVIEW.md](CONTENT_REVIEW.md) for the README claims and paths checked. See [SECURITY.md](SECURITY.md) for connection review guidance.
