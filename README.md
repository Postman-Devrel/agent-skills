<p align="center">
  <img src="https://voyager.postman.com/logo/postman-logo-orange.svg" alt="Postman" width="320">
</p>

# Postman Agent Skills

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Give your AI coding agent full access to Postman. Sync collections, generate client code, run tests, create mocks, publish docs, audit security, and analyze API readiness for AI agents.

Works with **Claude Code**, **Cursor**, **Windsurf**, **Codex**, and [40+ other agents](https://skills.sh).

## Install

```bash
npx skills add Postman-Devrel/agent-skills
```

This installs two skills:

| Skill | What It Does |
|-------|-------------|
| **postman** | Full API lifecycle: sync specs, generate code, run tests, create mocks, publish docs, audit security |
| **postman-api-readiness** | Analyze any API for AI agent compatibility (48 checks, 8 pillars, 0-100 scoring) |

## Prerequisites

1. **Postman API Key**: Get one at [postman.postman.co/settings/me/api-keys](https://postman.postman.co/settings/me/api-keys)

2. **Set the environment variable**:
   ```bash
   export POSTMAN_API_KEY=PMAK-your-key-here
   ```
   Add to `~/.zshrc` or `~/.bashrc` to persist.

3. **Postman MCP Server**: The skills use Postman's MCP Server for all operations. If you're using the [Postman Claude Code Plugin](https://github.com/Postman-Devrel/postman-claude-code-plugin), MCP is already configured. Otherwise, add to your MCP config:
   ```json
   {
     "mcpServers": {
       "postman": {
         "type": "http",
         "url": "https://mcp.postman.com/mcp",
         "headers": {
           "Authorization": "Bearer ${POSTMAN_API_KEY}"
         }
       }
     }
   }
   ```

## What You Can Do

### Sync Collections
Push OpenAPI specs to Postman, create collections, keep everything in sync.
```
"Sync my OpenAPI spec to Postman"
"Create a collection from my local API spec"
"Push my endpoint changes to Postman"
```

### Generate Client Code
Generate typed clients from your Postman collections in TypeScript, Python, Go, Rust, Java, or Ruby.
```
"Generate a TypeScript client from my Users API collection"
"Create a Python SDK for the Pet Store API"
```

### Run Tests
Execute Postman collection tests, diagnose failures, and fix code.
```
"Run the tests for my API collection"
"Why are my API tests failing?"
```

### Create Mock Servers
Spin up mock servers for frontend development and testing.
```
"Create a mock server for my collection"
"I need a fake API for frontend development"
```

### Publish Documentation
Analyze, improve, and publish API docs.
```
"How complete is my API documentation?"
"Generate docs for my OpenAPI spec"
"Publish my collection docs"
```

### Security Audit
Audit APIs against OWASP API Security Top 10.
```
"Run a security audit on my API"
"Check my spec for vulnerabilities"
```

### API Readiness Analysis
Score your API for AI agent compatibility.
```
"Is my API agent-ready?"
"Scan my OpenAPI spec for agent compatibility"
"How do I get my API to a 90% readiness score?"
```

## Skills Structure

```
skills/
  postman/
    SKILL.md                    # Main skill (7 workflows)
    references/
      mcp-tools.md              # MCP tool catalog
      mcp-limitations.md        # Known limitations + workarounds
  postman-api-readiness/
    SKILL.md                    # Readiness analyzer (48 checks)
    references/
      pillars.md                # Full pillar reference
```

## About

Built by the [Postman Developer Relations](https://www.postman.com) team. These skills give AI coding agents native access to Postman's API platform, turning your agent into a full API development partner.

The **postman** skill covers the complete API lifecycle: design, build, test, secure, deploy, observe, and distribute. The **postman-api-readiness** skill is a standalone analyzer that evaluates any OpenAPI spec for AI agent compatibility using a framework of 48 checks across 8 pillars.

## License

MIT
