# Security policy

## Reporting a vulnerability

**Do not open a public issue, pull request or discussion for a vulnerability.**

Report it privately:

- **GitHub private vulnerability reporting** (preferred): the "Report a vulnerability"
  button under the Security tab of the affected repository.
- **Email**: hey@openfsp.org.

If you can, include: the affected component and version, what an attacker can achieve, the
steps to reproduce, and any proof of concept.

I read French, Haitian Creole and English.

## Response times

| Step | Target |
|---|---|
| Acknowledgement | 72 hours |
| First assessment and severity | 7 days |
| Fix for critical severity | 14 days |
| Fix for high severity | 30 days |
| Fix for moderate or low severity | next planned release |

If a time frame has to be exceeded, I tell you before the deadline, with the reason.

These time frames rest on me alone, as the only editor
([GOVERNANCE.md 1](GOVERNANCE.md#1-steward)): they are best-effort commitments, not
contractual guarantees. I will revise them publicly if the project's capacity changes.

## Disclosure

Coordinated disclosure:

- I work with you on a fix and credit you in the security advisory, unless you decline.
- I publish a GitHub Security Advisory, with a CVE where applicable.
- I ask you to hold public disclosure until a fix is published, or for **90 days** from
  your report, whichever comes first. After 90 days, you are free to publish whatever the
  state of the fix.
- In case of active exploitation, I disclose and publish without waiting for the 90-day
  deadline.

Under [GOVERNANCE.md 6](GOVERNANCE.md#6-security-governance), a security fix may be
published ahead of the usual decision process; the decision documenting it is published
together with the fix.

## Scope

**In scope**: every repository published under the OpenFSP project, namely the
specification (a security flaw at protocol level is a vulnerability), the gateway, the
simulator, the SDKs and the conformance suite.

**Out of scope**

- Vulnerabilities in a payment provider's own systems: report them to the provider. A flaw
  in how *the OpenFSP adapter* handles that provider is in scope.
- Misconfiguration of a deployment you do not operate: report it to its operator.
- Automated scanner results without demonstrated impact.
- Social engineering, physical attacks, or denial of service by traffic volume.

## Deployment security

The OpenFSP gateway is **self-hosted**: the operator holds the provider secrets, and the
project runs no hosted service and handles no funds. See the
[architecture](https://openfsp.org/docs/architecture).

The project answers for defects in the published software; the operator answers for its
configuration and operation. A hardening guide for operators will ship with the gateway.

## No bounty program

No financial reward. I credit researchers in the security advisory, unless they decline.
