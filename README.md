# Awesome MCP Security [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of security tools, frameworks, scanners, gateways, and resources for the Model Context Protocol (MCP).

MCP is an open protocol that standardizes how AI agents connect to external tools and data sources. As adoption grows, so does the attack surface. This list tracks the ecosystem of projects working to make MCP safer.

## Contents

- [Scanners and Auditors](#scanners-and-auditors)
- [Gateways and Proxies](#gateways-and-proxies)
- [Firewalls and Guardrails](#firewalls-and-guardrails)
- [Observability and Tracing](#observability-and-tracing)
- [Redaction and Data Protection](#redaction-and-data-protection)
- [Access Control and Authorization](#access-control-and-authorization)
- [Authentication](#authentication)
- [Offensive Security and Testing](#offensive-security-and-testing)
- [Guides and Best Practices](#guides-and-best-practices)
- [Research and Standards](#research-and-standards)

---

## Scanners and Auditors

Tools that inspect MCP servers for vulnerabilities, misconfigurations, and malicious behavior.

- [invariantlabs-ai/mcp-scan](https://github.com/invariantlabs-ai/mcp-scan) - Detects prompt injection, tool poisoning, and other security issues in MCP servers. By Invariant Labs.
- [snyk/agent-scan](https://github.com/snyk/agent-scan) - Security scanner for AI agents, MCP servers, and agent skills. By Snyk.
- [cisco-ai-defense/mcp-scanner](https://github.com/cisco-ai-defense/mcp-scanner) - Scans MCP servers for potential threats and security findings. By Cisco AI Defense.
- [tayler-id/mcphound](https://github.com/tayler-id/mcphound) - Comprehensive MCP security scanner covering attack paths, tool poisoning, typosquats, CVEs, trust scores, and rug-pull detection.
- [tamish560/mcprobe](https://github.com/tamish560/mcprobe) - Security scanner for MCP servers. Detects prompt injection in tool descriptions, tool shadowing, and drift (rug-pull). Single binary, zero dependencies, Go stdlib only. Outputs text, JSON, and SARIF.
- [ModelContextProtocol-Security/mcpserver-audit](https://github.com/ModelContextProtocol-Security/mcpserver-audit) - Audits MCP servers for security problems before use. Part of the Cloud Security Alliance MCP Security initiative.
- [slowmist/MCP-Security-Checklist](https://github.com/slowmist/MCP-Security-Checklist) - Comprehensive security checklist for MCP-based AI tools. By SlowMist.
- [MCPGuard](https://usemcpguard.io/) - Security scanner for MCP servers. Commercial with free tier.

## Gateways and Proxies

Infrastructure that sits between MCP clients and servers to enforce policy, log traffic, and control access.

- [valtors/observer](https://github.com/valtors/observer) - Transparent MCP proxy for agent observability. SQLite trace storage, metadata-only by default, redaction patterns, session isolation. By Valtors.
- [reaatech/mcp-gateway](https://github.com/reaatech/mcp-gateway) - Production MCP gateway with OAuth/OIDC, API key auth, per-tenant rate limiting, schema enforcement, tool allowlists, audit trail.
- [lasso-security/mcp-gateway](https://github.com/lasso-security/mcp-gateway) - Plugin-based gateway that orchestrates MCPs with enterprise-grade security. By Lasso Security.
- [enkryptai/secure-mcp-gateway](https://github.com/enkryptai/secure-mcp-gateway) - Admin-level gateway with guardrails at each MCP server to prevent security issues.
- [qm-labs/agent-mcp-gateway](https://github.com/qm-labs/agent-mcp-gateway) - Per-subagent MCP access controls. Loads only 3 tools instead of all definitions. Prevents context window bloat.
- [sparfenyuk/mcp-proxy](https://github.com/sparfenyuk/mcp-proxy) - Bridge between Streamable HTTP and stdio MCP transports.
- [smart-mcp-proxy/mcpproxy-go](https://github.com/smart-mcp-proxy/mcpproxy-go) - Go-based MCP proxy with security features.

## Firewalls and Guardrails

Runtime enforcement tools that block malicious requests, detect threats, and apply policies.

- [ressl/mcp-firewall](https://github.com/ressl/mcp-firewall) - Open-source security gateway for AI agents. Policy enforcement, threat detection, compliance-ready audit logging.
- [General-Analysis/mcp-guard](https://github.com/General-Analysis/mcp-guard) - Secures MCP clients from prompt injection attacks and other threats.
- [GenTelLab/MCP-Guard](https://github.com/GenTelLab/MCP-Guard) - Multi-stage defense-in-depth framework for securing MCP in agentic AI. Research-backed.
- [promptfoo](https://www.promptfoo.dev/docs/red-team/mcp-security-testing/) - Red-team testing framework with MCP proxy for enterprise security testing.

## Observability and Tracing

Tools that log, trace, and monitor MCP interactions for debugging, auditing, and incident response.

- [traceloop/opentelemetry-mcp-server](https://github.com/traceloop/opentelemetry-mcp-server) - Unified MCP server for querying OpenTelemetry traces across Jaeger, Tempo, Traceloop.
- [xprilion/mcp-telemetry](https://github.com/xprilion/mcp-telemetry) - Adds tracing to all MCP client conversations for debugging and reporting.
- [theharithsa/opentelemetry-instrumentation-mcp](https://github.com/theharithsa/opentelemetry-instrumentation-mcp) - Automatic OpenTelemetry instrumentation for the MCP TypeScript SDK.
- [ContexaAI/mcp-trace-js](https://github.com/ContexaAI/mcp-trace-js) - Tracing middleware for MCP servers in TypeScript. Logs to file, DB, or cloud with OTLP, Supabase, PostgreSQL adapters.
- [Datadog LLM Observability](https://www.datadoghq.com/blog/mcp-client-monitoring/) - End-to-end visibility into MCP clients with Datadog.

## Redaction and Data Protection

Tools that prevent sensitive data from reaching LLMs through MCP tool calls.

- [r3352/redact-mcp](https://github.com/r3352/redact-mcp) - MCP server that auto-obfuscates sensitive data. Regex and AI-powered NER detection.
- [Strac MCP DLP](https://www.strac.io/blog/mcp-dlp) - Data loss prevention for MCP deployments. Prevents sensitive data exfiltration through MCP tools.

## Access Control and Authorization

Tools for restricting which tools agents can call and managing permissions.

- [Microsoft Agent Governance Toolkit](https://github.com/microsoft/agent-governance-toolkit) - Specification for MCP security gateways and agent governance in enterprise environments.
- [clerk/mcp-tools](https://github.com/clerk/mcp-tools) - Tools for building secure MCP integrations across client and server side. By Clerk.
- [Sandbox0 MCP Access Control](https://sandbox0.ai/blog/2026-05/mcp-tool-access-control-protocol-controls) - Restrict which tools AI agents can call through protocol-level controls.

## Authentication

Tools and libraries for authenticating MCP clients and servers.

- [mcpauth/mcpauth](https://github.com/mcpauth/mcpauth) - Authentication for MCP servers. OAuth 2.1 implementation.
- [MCP Auth specification](https://modelcontextprotocol.io/docs/tutorials/security/authorization) - Official MCP authorization documentation.

## Offensive Security and Testing

Tools for penetration testing MCP deployments and security research.

- [cyproxio/mcp-for-security](https://github.com/cyproxio/mcp-for-security) - MCP servers for security tools: SQLMap, FFUF, NMAP, Masscan. Integrate pentesting into AI workflows.
- [FuzzingLabs/mcp-security-hub](https://github.com/FuzzingLabs/mcp-security-hub) - Offensive security MCP servers: Nmap, Ghidra, Nuclei, SQLMap, Hashcat.
- [securityfortech/secops-mcp](https://github.com/securityfortech/secops-mcp) - All-in-one security testing toolbox through a single MCP interface. Pentesting, bug bounty, threat hunting.
- [Puliczek/awesome-mcp-security](https://github.com/Puliczek/awesome-mcp-security) - List of MCP security exploits, POCs, writeups, and bug bounty resources.

## Guides and Best Practices

- [MCP Security Best Practices (Official)](https://modelcontextprotocol.io/docs/tutorials/security/security_best_practices) - Official security best practices from the MCP specification team.
- [OWASP MCP Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/MCP_Security_Cheat_Sheet.html) - OWASP cheat sheet for securing MCP implementations.
- [OWASP MCP Top 10](https://owasp.org/www-project-mcp-top-10/) - OWASP's top 10 security risks for Model Context Protocol.
- [OWASP Secure MCP Server Development Guide](https://genai.owasp.org/resource/a-practical-guide-for-secure-mcp-server-development/) - Practical guide for developers building MCP servers securely.
- [Microsoft MCP for Beginners - Security](https://github.com/microsoft/mcp-for-beginners/blob/main/02-Security/mcp-best-practices.md) - Microsoft's security module for MCP beginners.
- [Red Hat: MCP Security Risks and Controls](https://www.redhat.com/en/blog/model-context-protocol-mcp-understanding-security-risks-and-controls) - Enterprise perspective on MCP security risks.
- [Microsoft: Protecting Against Indirect Prompt Injection in MCP](https://developer.microsoft.com/blog/protecting-against-indirect-injection-attacks-mcp) - How to defend against indirect prompt injection attacks via MCP.

## Research and Standards

- [NSA MCP Security Guide (PDF)](https://media.defense.gov/2026/Jun/02/2003943289/-1/-1/0/CSI_MCP_SECURITY.PDF) - NSA Cybersecurity Information sheet on MCP security.
- [Cloud Security Alliance: Agentic MCP Security Best Practices](https://labs.cloudsecurityalliance.org/agentic/agentic-mcp-security-best-practices-v1/) - CSA best practices for agentic MCP security.
- [MCP-Guard: Defense-in-Depth Framework (Paper)](https://arxiv.org/abs/2508.10991) - Academic paper on multi-stage defense framework for MCP.
- [MindGuard: Tool Poisoning Detection (Paper)](https://arxiv.org/html/2508.20412v1) - Research on tracking, detecting, and attributing MCP tool poisoning attacks.
- [SecAppDev 2026: MCP Security](https://secappdev.org/2026/sessions/model-context-protocol-mcp-security) - Conference session on MCP security fundamentals.

---

## Contributing

Contributions are welcome. Please read the [contributing guidelines](CONTRIBUTING.md) before submitting a pull request.
