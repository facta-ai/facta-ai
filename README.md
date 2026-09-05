<div align="center">

# Facta

**The auditable fact ledger for AI agents.**

Facta is an open-source system for managing structured, verifiable facts and the relationships between them. It gives AI agents a shared source of truth that can be inspected, updated, cited, and reviewed instead of being hidden inside isolated prompts or conversations.

[![License](https://img.shields.io/github/license/xieshiqi147258/facta-ai?style=flat)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/xieshiqi147258/facta-ai?style=flat)](https://github.com/xieshiqi147258/facta-ai/stargazers)

</div>

---

## What is Facta?

AI agents are good at producing answers, but their context is fragmented across chats, files, tools, and memory systems. The same server, project, or service may be described differently by different agents, and nobody can easily tell which statement is current, where it came from, or who changed it.

Facta treats facts as explicit, reviewable assets. Each fact has a subject, predicate, value, source, confidence, status, timestamp, and history. Facts can be connected into a topology so agents understand not only isolated values, but also the systems and dependencies around them.

**Agents share evidence-backed context without sharing opaque memory.**

## Core capabilities

- **Assets** - Represent servers, machines, software, services, projects, domains, accounts, and other objects.
- **Facts** - Store structured claims such as versions, ports, deployment locations, ownership, and operational status.
- **Relations** - Connect assets through typed relationships such as `runs_on`, `depends_on`, `deployed_at`, and `connects_to`.
- **Evidence** - Preserve where a fact came from, when it was observed, and how it can be verified.
- **History** - Keep changes auditable so current state never erases the path that produced it.
- **Agent context** - Provide the same structured facts to multiple agents, tools, and interfaces.

## Core concepts

| Concept | Description |
| --- | --- |
| Asset | A managed object with an identity and lifecycle. |
| Fact | A structured, time-aware claim about an asset. |
| Relation | A typed connection between two assets. |
| Evidence | The source supporting a fact. |
| Proposal | A suggested fact or change awaiting review. |
| History | The append-only record of changes and decisions. |
| Topology | The connected graph of assets and relations. |

```text
subject    predicate       value             evidence             status
server-01  listens_on      8080              deployment-check     verified
```

## Typical workflow

1. Register an asset.
2. Record an observation with source, timestamp, and verification details.
3. Connect the asset to related machines, services, repositories, and dependencies.
4. Let agents query the current facts and surrounding context.
5. Review proposed changes before they become authoritative.
6. Audit the evidence and history behind every important update.

## Architecture

```text
        Web / Desktop / CLI / MCP clients
                       │
                       ▼
              ┌─────────────────┐
              │  Facta context  │
              │  and query API  │
              └────────┬────────┘
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
     Asset store   Fact ledger   Topology graph
          │            │            │
          └────────────┼────────────┘
                       ▼
             Evidence and history
```

Facta is designed around a local-first, auditable data model. The interface can evolve independently from the ledger, while storage and synchronization layers can support local deployments, shared infrastructure, and controlled API or WebDAV distribution.

## Design principles

- Facts over hidden memories
- Evidence over confidence alone
- Proposal before authority
- History is part of state
- Local data first
- Interoperability by default

## Status and roadmap

Facta is under active development. Current work focuses on the asset ledger experience, topology visualization, fact history, agent-facing context access, and a desktop foundation for local-first operation.

Planned areas include persistent local storage, fact and relation APIs, MCP integration, proposal and conflict-resolution workflows, evidence adapters, multi-device synchronization, access control, and portable import/export.

## Documentation

- [Project plans](docs/superpowers/plans/)
- [Research and architecture notes](docs/multica-research/)

## Contributing

Issues and pull requests are welcome. For substantial changes, please describe the data model, user workflow, and audit implications involved.

## License

License information will be added as the project reaches its first public development milestone.
