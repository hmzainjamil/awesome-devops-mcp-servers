# awesome-devops-mcp-servers

> **Curated list of DevOps MCP servers — CI/CD, infrastructure, monitoring, deployment, cloud, security integrations**

<p align="center">
  <a href="https://github.com/hmzainjamil/awesome-devops-mcp-servers/stargazers"><img src="https://img.shields.io/github/stars/hmzainjamil/awesome-devops-mcp-servers?style=for-the-badge&labelColor=555&color=yellow" alt="Stars"/></a>
  <a href="https://github.com/hmzainjamil/awesome-devops-mcp-servers/network/members"><img src="https://img.shields.io/github/forks/hmzainjamil/awesome-devops-mcp-servers?style=for-the-badge&labelColor=555&color=blue" alt="Forks"/></a>
  <a href="https://github.com/hmzainjamil/awesome-devops-mcp-servers/issues"><img src="https://img.shields.io/github/issues/hmzainjamil/awesome-devops-mcp-servers?style=for-the-badge&labelColor=555&color=red" alt="Issues"/></a>
  <a href="https://github.com/hmzainjamil/awesome-devops-mcp-servers/pulls"><img src="https://img.shields.io/github/issues-pr/hmzainjamil/awesome-devops-mcp-servers?style=for-the-badge&labelColor=555&color=purple" alt="PRs"/></a>
  <a href="https://github.com/hmzainjamil/awesome-devops-mcp-servers/commits/main"><img src="https://img.shields.io/github/last-commit/hmzainjamil/awesome-devops-mcp-servers?style=for-the-badge&labelColor=555&color=green" alt="Last Commit"/></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Awesome-list-red?style=flat&labelColor=555&logo=awesome"/>
  <img src="https://img.shields.io/badge/MCP-protocol-blue?style=flat&labelColor=555"/>
  <img src="https://img.shields.io/badge/DevOps-focused-orange?style=flat&labelColor=555"/>
  <img src="https://img.shields.io/badge/License-MIT-lightgrey?style=flat&labelColor=555"/>
</p>

---

## Why This Exists

MCP (Model Context Protocol) lets AI models interact with real tools — but the ecosystem is scattered. This list curates only DevOps-relevant MCP servers: cloud infrastructure, CI/CD, monitoring, security, databases, containers, and deployment tools. Stop hunting through 500-item general lists.

---

## At a Glance

| Category | Count | Examples |
|---|---|---|
| Cloud Infrastructure | 20+ | AWS, GCP, Azure, Terraform |
| CI/CD | 15+ | GitHub Actions, CircleCI, Jenkins |
| Containers | 10+ | Docker, Kubernetes, Helm |
| Monitoring | 12+ | Grafana, Prometheus, Datadog |
| Security | 8+ | Vault, SAST, secrets scanning |
| Databases | 15+ | PostgreSQL, Redis, MongoDB |
| Version Control | 8+ | GitHub, GitLab, Bitbucket |
| Incident Response | 6+ | PagerDuty, OpsGenie |
| Networking | 7+ | Cloudflare, ngrok, Nginx |
| Observability | 10+ | OpenTelemetry, Jaeger, Zipkin |

---

## 🧠 CONCEPTS

| Concept | Description |
|---|---|
| **MCP** | Model Context Protocol — open standard for AI↔tool communication |
| **MCP server** | Process exposing tools to Claude via stdio or HTTP |
| **Tool** | Callable function exposed by MCP server — typed input/output |
| **Resource** | File/data accessible to Claude via MCP |
| **Official** | 🎖️ — maintained by the tool's primary vendor |
| **Transport** | `stdio` (local) or `http` (remote) — how Claude connects |
| **mcp.json** | Config file specifying which servers Claude loads |
| **Scope** | ☁️ Cloud service, 🏠 Local, 📟 Embedded |
| **Language** | 🐍 Python, 📇 TypeScript, 🏎️ Go, 🦀 Rust, #️⃣ C#, ☕ Java |
| **Capability** | What operations the server exposes: read, write, execute |

### 🔥 Hot

- **Infrastructure-as-code MCP** — Terraform MCP lets Claude plan, apply, and destroy infrastructure directly from chat
- **GitHub Actions MCP** — trigger CI runs, check status, read logs without leaving Claude context
- **Kubernetes MCP** — `kubectl get pods`, apply manifests, view logs — full cluster management via natural language
- Source → [HMZ](https://github.com/hmzainjamil)

---

## ⚙️ HOW IT WORKS

```
# 1. Install MCP server
pip install mcp-server-kubernetes  # or npm install, etc.

# 2. Add to Claude config
# .claude/mcp.json:
{
  "mcpServers": {
    "kubernetes": {
      "command": "mcp-server-kubernetes",
      "args": ["--kubeconfig", "~/.kube/config"]
    }
  }
}

# 3. Claude now has k8s tools
# "List all pods in production namespace"
# "Scale deployment api-server to 5 replicas"
```

---

## 🚀 INSTALL

```bash
# Clone list
git clone https://github.com/hmzainjamil/awesome-devops-mcp-servers

# Install a specific server (example: GitHub)
npm install -g @modelcontextprotocol/server-github

# Add to Claude
echo '{"mcpServers": {"github": {"command": "mcp-server-github", "env": {"GITHUB_TOKEN": "your-token"}}}}' > .claude/mcp.json
```

---

## 📟 USAGE

```bash
# Find servers by category
grep -A5 "## CI/CD" README.md

# Test server connectivity
claude --mcp-debug

# List active MCP tools
# In Claude: "What tools do you have available?"
```

---

## ⚙️ CONFIGURATION

| Field | Required | Description |
|---|---|---|
| `command` | ✓ | Executable to run |
| `args` | optional | CLI arguments |
| `env` | optional | Environment variables |
| `cwd` | optional | Working directory |
| `transport` | optional | `stdio` (default) or `http` |
| `url` | HTTP only | Remote server URL |
| `headers` | HTTP only | Auth headers |
| `timeout` | optional | Request timeout ms |
| `disabled` | optional | Set true to disable without removing |
| `alwaysAllow` | optional | Tool names to skip approval prompts |

---

## 💡 TIPS AND TRICKS

### Performance
1. **Test servers locally first** — `npx @modelcontextprotocol/inspector mcp-server-name` opens a web UI to test tools before wiring to Claude. Source → [HMZ](https://github.com/hmzainjamil)
2. **Minimal permissions** — each MCP server gets only the API keys/permissions it needs. Never give infrastructure servers write access unless required. Source → [HMZ](https://github.com/hmzainjamil)
3. **Local vs remote** — prefer local stdio servers for security. HTTP transport exposes your tools to network. Source → [HMZ](https://github.com/hmzainjamil)

### Integration
4. **Combine servers** — Terraform + AWS + GitHub Actions together = full deploy-from-chat workflow. Source → [HMZ](https://github.com/hmzainjamil)
5. **Always-allow low-risk** — add read-only tools to `alwaysAllow` in mcp.json to avoid approval prompts. Source → [HMZ](https://github.com/hmzainjamil)
6. **Environment isolation** — use `.env.local` for API keys, never commit to repo. Source → [HMZ](https://github.com/hmzainjamil)

### Advanced
7. **Version pin servers** — `@1.2.3` not `latest` in mcp.json for reproducible setups. Source → [HMZ](https://github.com/hmzainjamil)
8. **Health check MCP** — write a minimal `health_check` tool in each server that returns status — useful for debugging. Source → [HMZ](https://github.com/hmzainjamil)
9. **Logging** — set `DEBUG=mcp:*` env var to see all MCP protocol messages. Source → [HMZ](https://github.com/hmzainjamil)

### Debugging
10. **Rate limiting** — wrap expensive API calls with rate limiter in custom servers. Source → [HMZ](https://github.com/hmzainjamil)
11. **Error handling** — return structured errors from tools, not thrown exceptions — Claude reads error messages. Source → [HMZ](https://github.com/hmzainjamil)
12. **Async tools** — long-running operations should return a job ID, then expose a `check_status(job_id)` tool. Source → [HMZ](https://github.com/hmzainjamil)

---

## 🔧 TROUBLESHOOTING

| Issue | Cause | Fix |
|---|---|---|
| Server not found in Claude | Not in mcp.json | Add server definition |
| Tool calls fail | Wrong API key | Check env vars in mcp.json |
| Server crashes on start | Missing dependency | Check server README for deps |
| Timeout on tool call | Operation too slow | Increase timeout in mcp.json |
| Permission denied | Scope too narrow | Check API key permissions |
| Tools not showing | Server not running | `claude --mcp-debug` |
| Approval every call | Not in alwaysAllow | Add tool name to alwaysAllow list |

---

## 📊 ARCHITECTURE

```
Claude Code
    ↓ stdio / HTTP
[MCP Server A]    [MCP Server B]    [MCP Server C]
  Kubernetes         GitHub            Terraform
     ↓                 ↓                  ↓
  kubectl API      GitHub API        Terraform CLI
```

---

## 🗺️ ROADMAP

- [ ] Interactive filtering by language/scope/stars
- [ ] Automated uptime testing of listed servers
- [ ] mcp.json snippets for common DevOps stacks
- [ ] Video walkthroughs for top 10 servers
- [ ] Community voting on best servers per category

---

## ☠️ STARTUPS / BUSINESSES

DevOps MCP servers turn Claude into a full infrastructure management console. Engineers spend less time on CLI context-switching. Incident response is faster when Claude can query Grafana, check PagerDuty, and read k8s logs in one conversation.

**Agency value:** automate client infrastructure reports, deployment status checks, and cost analysis with MCP-wired Claude sessions.

---

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=hmzainjamil/awesome-devops-mcp-servers&type=Date)](https://star-history.com/#hmzainjamil/awesome-devops-mcp-servers&Date)

---

<p align="center">
  Built by <a href="https://github.com/hmzainjamil">HMZ</a> · <a href="https://github.com/hmzainjamil/awesome-devops-mcp-servers/issues">Issues</a> · <a href="https://github.com/hmzainjamil/awesome-devops-mcp-servers/pulls">PRs</a>
</p>
