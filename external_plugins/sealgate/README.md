# SealGate

Connect agents to everything and manage agent access. SealGate manages adding, 
monitoring, enforcing policies, blocking data exfiltration at runtime for any MCP.
Flexible CLI, API, MCP interfaces available.

- Website: https://sealgate.ai
- Dashboard: https://dashboard.sealgate.ai
- Docs: https://docs.sealgate.ai

## What this plugin does

It connects Grok to the SealGate MCP gateway as a single composite MCP server.
Once connected, the tools from every downstream server you have enabled in your
SealGate dashboard become available to Grok, with SealGate's policy engine
enforcing PUBLIC / PRIVATE / SECRET access levels and lethal-trifecta blocking
on every call.

## Requirements

- A SealGate account. Sign in / sign up at https://dashboard.sealgate.ai.

## How it connects (OAuth 2.1)

The plugin declares one remote MCP server pointing at `https://mcp.sealgate.ai/mcp`. No credentials are stored in the listing. The client discovers the authorization server from the 401 `WWW-Authenticate` challenge, does DCR/CIMD + PKCE, and you approve access on the SealGate consent screen. Each installing user authenticates as themselves.
