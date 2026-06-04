# @geek4good/pi-setup

A lean Pi package for software development, security consulting, web performance auditing, and research.

## What's Included

### Extensions (8)

| Extension | Description |
|---|---|
| **security-guard** | Pre-tool hook: blocks destructive commands, detects prompt injection, prevents data exfiltration |
| **message-integrity-guard** | Prevents session-bricking from orphaned tool_result messages |
| **memory-cycle** | Memory-aware compaction — preserves context across compaction cycles |
| **footer** | Status bar — model name, context %, working directory |
| **escape-cancel** | Double-ESC cancels all running operations |
| **agent-banner** | ASCII art banner on startup |

Plus 2 lib modules: `agent-memory.ts` and `stable-checkpoint.ts`.

### Agents (12)

**Code & Quality**

| Agent | Use When |
|---|---|
| `knight` | Security vulnerability review — injection, secrets, auth bypass, config weaknesses |
| `red-team` | Adversarial testing — finds vulnerabilities and failure modes |
| `warden` | Quality gate synthesis — coordinates findings from multiple agents into consolidated reports |
| `paladin` | Surgical remediation — fixes findings while preserving existing behavior |
| `ranger` | Pattern/DRY enforcement — identifies duplication, enforces consistency |
| `tester` | Test creation and validation |

**Web Consulting**

| Agent | Use When |
|---|---|
| `perf-auditor` | Web performance auditing — Lighthouse, Core Web Vitals, network waterfalls, memory profiling |
| `web-security-scanner` | HTTP headers, SSL/TLS, CORS, CSP, cookie flags, dependency CVEs |
| `network-scout` | Passive network recon — interface and listener analysis |
| `port-scan-analyst` | Safe local port analysis with conservative profiles |
| `security-news-analyst` | Threat intelligence from CISA, NVD, OWASP, CVE |

**Documentation**

| Agent | Use When |
|---|---|
| `documenter` | Creates documentation using the Diataxis framework — tutorials, how-to guides, reference docs, explanations |

### Theme

**Midnight Ocean** — deep blue terminal theme.

## Install

### Prerequisites

Install the peer dependency packages first:

```bash
pi install npm:pi-web-access
pi install npm:pi-mcp-adapter
pi install npm:pi-subagents
pi install npm:pi-intercom
```

### Install this package

```bash
pi install git:github.com/ruizrica/pi-setup
```

Restart Pi after installation.

### Optional MCP Servers

For web performance and security auditing:

```json
{
  "mcpServers": {
    "chrome-devtools": {
      "command": "bunx",
      "args": ["chrome-devtools-mcp@latest"],
      "lifecycle": "lazy"
    }
  }
}
```

## Architecture

```
pi-setup/
├── package.json           ← Pi package manifest
├── README.md
├── extensions/
│   ├── security-guard.ts
│   ├── message-integrity-guard.ts
│   ├── memory-cycle.ts
│   ├── footer.ts
│   ├── escape-cancel.ts
│   ├── agent-banner.ts
│   └── lib/               ← Shared dependencies
│       ├── security-engine.ts
│       ├── themeMap.ts
│       ├── context-gate.ts
│       ├── memory-cycle-helpers.ts
│       └── output-box.ts
├── agents/
│   ├── knight.md
│   ├── red-team.md
│   ├── warden.md
│   ├── paladin.md
│   ├── ranger.md
│   ├── tester.md
│   ├── network-scout.md
│   ├── port-scan-analyst.md
│   ├── security-news-analyst.md
│   ├── perf-auditor.md
│   ├── web-security-scanner.md
│   └── documenter.md
└── themes/
    └── midnight-ocean.json
```

## Peer Dependencies

| Package | Role |
|---|---|
| `pi-subagents` | Agent orchestration — single/chain/parallel/fanout execution |
| `pi-intercom` | Parent-child messaging for background agent decisions |
| `pi-web-access` | Web search, code search, fetch_content |
| `pi-mcp-adapter` | Lazy-loaded MCP server integration |
| `beautiful-mermaid` | Terminal Mermaid diagram rendering (ASCII/Unicode) |

## License

MIT
