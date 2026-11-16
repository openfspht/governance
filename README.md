<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://cdn.openfsp.org/logo/openfsp-logo-inverse.svg">
  <img src="https://cdn.openfsp.org/logo/openfsp-logo.svg" alt="OpenFSP" width="320">
</picture>

**An open standard for payment integration in Haiti**

[![License](https://img.shields.io/badge/license-Apache--2.0-blue)](LICENSE)
[![Protocol](https://img.shields.io/badge/protocol-0.1.0-0B3B36)](https://openfsp.org/docs/status)

</div>

OpenFSP is one open contract between merchant applications and Haitian payment service
providers. A provider implements it once; a merchant application speaks it once and works
with every compatible provider.

This repository holds the governance: who decides, how decisions are made, and what
adopters can rely on.

## The idea

Without a shared contract, each of `L` merchant applications integrates each of `O`
providers: `O × L` integrations. With OpenFSP, each application speaks one protocol and
each provider implements that contract once: `O + L`.

```mermaid
flowchart LR
    apps["Merchant applications<br/><i>HTTP or SDK</i>"]
    subgraph std["OpenFSP contract"]
        G["Gateway<br/><i>self-hosted by the merchant</i>"]
        N["Native provider"]
    end
    apps --> G
    apps --> N
    G --> M["MonCash API"]
    G --> C["NatCash API"]
```

A native provider speaks OpenFSP directly. Until providers do, the gateway translates the
contract into the existing MonCash and NatCash APIs, so it is usable today.

## Components

| Component | Role |
|---|---|
| **Specification** | The contract: data model, lifecycle, capabilities, errors, idempotency, webhooks, authentication, conformance. |
| **Gateway** | One implementation, self-hosted by the merchant: OpenFSP in, MonCash and NatCash APIs out. |
| **Simulator** | Plays the providers, failures included, and a native OpenFSP provider, for testing without a merchant account. |
| **SDKs** | The next step: Kotlin for the JVM first, then TypeScript. The protocol also works over plain HTTP. |
| **Conformance suite** | Checks a gateway or a native provider against the specification; anyone can rerun it. |

## Links

- Specification, decisions and status: [openfsp.org](https://openfsp.org)
- Code: [openfspht/openfsp](https://github.com/openfspht/openfsp)
- Governance: [GOVERNANCE.md](GOVERNANCE.md), [CONTRIBUTING.md](CONTRIBUTING.md),
  [SECURITY.md](SECURITY.md)
- License: [Apache-2.0](LICENSE)

I take reviews and proposals through the decision process described in
[CONTRIBUTING.md](CONTRIBUTING.md).
