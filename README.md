# MCP Observe

Embeddable, OpenTelemetry-native observability and cryptographic audit SDK for [Model Context Protocol](https://modelcontextprotocol.io/) servers.

**Status:** Pre-release. PRD under review. Targeting v0.1 in 30 days.

---

## What this will be

A drop-in SDK (TypeScript and Python at v0.1) that any MCP server can import to emit:

- **OpenTelemetry traces, metrics, and logs** conforming to the [January 2026 `gen-ai/mcp` semantic conventions](https://opentelemetry.io/docs/specs/semconv/gen-ai/mcp/)
- A **separate cryptographic audit artifact** — hash-chained, Ed25519-signed digests in the CloudTrail mould — distinct from the observability pipeline so it satisfies ISO 27001 A.12.4.2, HIPAA §164.312(b), EU AI Act Article 12 retention, and SOC 2 CC7.2/CC7.3

…with sensible **redact-by-default** behaviour so tool arguments and results aren't capturing PII or secrets unless you explicitly opt in.

## Why now

The OTel MCP semantic conventions merged in January 2026 (PR #2083, semconv v1.34). Existing observability tools for MCP are either context-propagation only (Arize OpenInference), broken on the non-standard SDK module layout (Traceloop), or full Kubernetes-scale gateways (Stacklok ToolHive, IBM mcp-context-forge). There is no drop-in SDK middleware that just instruments your server, much less one that ships a tamper-evident audit plane alongside.

## Roadmap

The full design and 30-day execution plan lives in the PRD. Read it, comment on it, or open issues against it:

**📋 [PRD: MCP Observe v0.1 — Issue #1](https://github.com/togglekit-labs/mcp-observe/issues/1)**

## Licence

[Apache 2.0](./LICENSE) — patent grant included, by design. Embed this in commercial software without friction.

## Studio

Built by [ToggleKit Ltd](https://togglekit.dev), a small UK studio.
