# Security guidance for MCP servers

MCP servers can expose powerful actions. DevOps integrations may change deployments, infrastructure, CI settings, monitoring, or secrets. Review a server's code and tools before connecting it to an account.

- Use a separate test environment and least-privilege credentials.
- Confirm read/write effects and approval behavior for each tool.
- Inspect install commands, dependencies, network destinations, and secret storage.
- Do not send credentials or production data to unverified servers.
- Revoke tokens and remove the server configuration when access is no longer needed.

This repository is a discovery list, not a security review or endorsement. Report list-specific issues privately through GitHub if enabled. Contact upstream maintainers privately for vulnerabilities in their server. Do not publish credentials or exploit details.
