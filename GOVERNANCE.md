# Governance

I set out here who decides what, how I record decisions, what guarantees adopters receive,
and on what conditions I open the governance.

## 1. Steward

OpenFSP is published and stewarded by **Karako Systems** (Haiti, https://karakosystems.com),
which holds the project's governance, its repositories and its name.

Karako Systems appoints the **editor**, the project's technical decision maker, responsible
for the consistency of the specification and the decisions, and for publishing the
conformance suite.

**I am currently the only editor, with no other maintainer.** Opening conditions: section 7.

## 2. Declared interest

Karako Systems builds commercial products on top of OpenFSP. Four constraints govern this
interest:

1. **No privileged path.** Changes driven by a commercial product of the steward go through
   the same public decision process as any other change, under the same review, within the
   same time frames.
2. **Declared motivation.** When a decision is driven by a need of one of the steward's
   products, its *Decision* section says so.
3. **No lock-in through the specification.** The specification must not contain a
   requirement whose only purpose would be to favour one implementation. Any reviewer may
   challenge a provision on that ground, and I commit to answering the challenge publicly
   before publishing the provision.
4. **Feature access parity.** Every capability the steward's products use is part of the
   public specification. There is no undocumented extension.

Reference: article 85 of the law of 14 May 2012 on banks and other financial institutions
requires regulated institutions to act "fairly and equitably in the best interests of their
clients and the integrity of the market", and to "endeavour to avoid conflicts of interest
and, where they cannot be avoided, to ensure that their clients are treated fairly" (my
translation). Karako Systems is not a bank and is not bound by this article; the four
constraints follow its form.

## 3. License commitment

Karako Systems makes these commitments to every adopter of OpenFSP:

- **Everything published under OpenFSP is licensed under Apache-2.0**: specification,
  gateway, simulator, SDKs and conformance suite. No component is held back under another
  license.
- **No contributor license agreement.** Contributions fall under the Developer Certificate
  of Origin (see [CONTRIBUTING.md](CONTRIBUTING.md)). Contributors keep their copyright; no
  right is assigned to the steward.
- **Irrevocable grant.** Since contributions are assigned to no single owner, no decision of
  the steward can retroactively withdraw the Apache-2.0 grant on what has been published.
- **Right to fork.** The Apache-2.0 license lets anyone derive the project; the steward
  recognizes this remedy as legitimate.

## 4. How decisions are made

### Decision required

A written decision is a section of the [Decisions](https://openfsp.org/docs/decisions)
page, proposed by pull request on
[openfspht/openfsp.org](https://github.com/openfspht/openfsp.org). It is required for
anything that changes what a conforming implementation must do:

- Any change to the messages exchanged between client and gateway: resources, fields,
  status values, error codes.
- Any new capability, or any change to how capabilities are announced.
- Any change to the conformance requirements or to the meaning of the conformance suite.
- Any change to versioning, deprecation or security requirements.
- Removing or deprecating anything already specified.
- This document, and the decision process itself.

### Decision not required

A pull request is enough for:

- Implementation work that does not change specified behaviour: bug fixes, performance,
  refactoring, internal structure of the gateway or the SDKs.
- New provider adapters, when the provider fits the existing capability model. Otherwise, a
  written decision.
- Documentation, examples, tests, tooling, translations.
- Editorial corrections to a written decision that do not change its meaning.

If you are unsure which path applies, open an issue and ask.

### Resolution

I decide publicly, in the decision's pull request, with reasons. I seek consensus, without
making it a formal requirement while I am the only editor.

## 5. Stability guarantees

- **Semantic versioning of the specification**
  ([SemVer 2.0.0](https://semver.org/spec/v2.0.0.html)), `MAJOR.MINOR.PATCH`. A MAJOR
  increment may break conforming implementations; a MINOR increment adds a capability while
  staying backward compatible. Adaptation: a PATCH increment clarifies wording without
  changing behaviour.
- **Backward compatibility is not broken without a written decision.** No exception for
  urgency.
- **A deprecation requires notice of one full MAJOR version.** What is deprecated in `2.x`
  cannot be removed before `3.0`, and must be marked as deprecated in the specification, in
  the gateway's responses and in the release notes for that whole period.
- **Errata are tracked.** Published wording that is wrong or ambiguous is corrected in place
  by a commit that says so.
- **Exception before 1.0.** Before `1.0.0`, breaking changes may occur between MINOR
  versions. Each one requires a written decision.

## 6. Security governance

Vulnerability reports follow [SECURITY.md](SECURITY.md) and are handled privately until a
fix is available.

A security fix may be published without a prior public decision when disclosure would put
deployments at risk. The decision documenting the change is then published with the fix.
Security is the only ground on which the decision requirement may be deferred.

## 7. Opening the governance

A **Technical Steering Committee (TSC)** is established as soon as one of these conditions
is met:

- **(a)** Three or more people outside Karako Systems have each completed substantial,
  independent contributions (a written decision, a provider adapter, or a maintained SDK)
  and agree to sit on it; or
- **(b)** A payment provider, a financial institution or a public authority adopts OpenFSP
  in production or formally supports it.

On establishment:

- The TSC holds final authority over the specification. The editor has one vote like the
  other members.
- Karako Systems holds at most **one third** of the seats, rounded down, whatever share of
  the work it has done.
- Seats are held by individuals, named publicly, with their affiliation declared.
- Decisions are made by simple majority of the sitting members, publicly, with recorded
  reasons.
- The OpenFSP name is transferred under section 8.
- The TSC's first task is to ratify or amend this document.

## 8. Name and conformance marks

The OpenFSP name and any conformance mark ("OpenFSP conformant", or a similar phrase) are
held by Karako Systems and are not granted by the Apache-2.0 license, which covers the
software and the text, not trademarks.

Karako Systems holds this name as a **custodian**, for the project, and commits to:

- **No power to grant.** Karako Systems can neither grant nor refuse a conformance claim:
  under the rules below, a claim depends on a published report, for the steward as for
  everyone.
- **No unilateral change.** Once the TSC is established (section 7), the rules for using the
  name and this section can be changed only with the TSC's agreement.
- **Transfer to the TSC.** Within twelve months of the TSC's establishment, Karako Systems
  assigns the OpenFSP name, and any registered trademark attached to it, free of charge to a
  legal entity designated by the TSC. Until that assignment, Karako Systems grants the TSC a
  free and irrevocable license to use the name for the project's needs.

These commitments hold whether or not the name is registered: if it is not, they cover its
use; if it is, they cover the registration itself.

**Claiming conformance.** There is no certification program, no fee and no license:

- A claim states a result of the
  [conformance suite](https://openfsp.org/docs/spec/conformance). It rests on a passing
  report published with its configuration, for the claimed version of the implementation.
  Everyone runs the suite themselves: no submission, no approval.
- Form: `OpenFSP conformant <target>, <level>, protocol <version>`, followed by the profiles
  passed, with access to the report. Accepted short form: "OpenFSP conformant (Core,
  0.1.0)", never "OpenFSP conformant" alone. The word is "conformant", never certified,
  approved, validated, endorsed, accredited or compliant.
- Forbidden: implying that a third party certified or approved, omitting the version,
  claiming a profile not passed, presenting conformance as a security assurance, passing a
  product off as a product of the project, claiming conformance because an adapter exists.
- A false claim is first notified to its author, then reported publicly with the evidence
  if it is not corrected. There is no grant and no revocation: a claim is invalid as soon as
  the published report can no longer be reproduced with the declared configuration.
- The steward's implementations follow exactly this path, published in the same place.

Describing your work as "built on OpenFSP" or "implements OpenFSP `<version>`" remains
free: these are not conformance claims.

## 9. Amending this document

Changes to this document require a written decision, with one exception: the establishment
of the TSC under section 7 happens automatically as soon as its trigger is met, and needs no
decision to take effect.

---

*Questions about governance: hey@openfsp.org*
