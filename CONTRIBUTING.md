# Contributing to OpenFSP

Who decides what and which guarantees apply: [GOVERNANCE.md](GOVERNANCE.md).

## Response times

OpenFSP has one editor ([GOVERNANCE.md 1](GOVERNANCE.md#1-steward)). We aim for a first
review within 7 days, and review short contributions limited to one topic first.
For a large change, open an issue first.

## Choosing a path

### Open an issue when

You found a bug or an ambiguity in the specification, or want to discuss an idea. We treat
any sentence that two implementers read differently as a defect of the specification, even
if the current implementations agree.

### Open a pull request when

The change does not alter what a conforming implementation must do. List:
[GOVERNANCE.md 4](GOVERNANCE.md#4-how-decisions-are-made), *Decision not required*.

### Propose a decision when

The change alters what a conforming implementation must do. List:
[GOVERNANCE.md 4](GOVERNANCE.md#4-how-decisions-are-made), *Decision required*.
Procedure: a pull request that adds a section to the
[Decisions](https://openfsp.org/docs/decisions) page, on
[openfspht/openfsp.org](https://github.com/openfspht/openfsp.org).

## Where things live

- Specification and decisions: [openfspht/openfsp.org](https://github.com/openfspht/openfsp.org),
  published on [openfsp.org](https://openfsp.org).
- Gateway, simulator, SDKs and conformance suite:
  [openfspht/openfsp](https://github.com/openfspht/openfsp).
- Governance: [openfspht/governance](https://github.com/openfspht/governance), this
  repository.

## Licensing of contributions

OpenFSP uses no contributor license agreement and no sign-off: you keep your copyright.
Under section 5 of the [Apache License 2.0](LICENSE), a contribution you submit is
licensed under the same terms as the project.

## Repository conventions

**Language.** Everything in the repositories is in English. The site
[openfsp.org](https://openfsp.org) is also published in French. Issues may be written in
English, French or Haitian Creole.

**Commit messages.** Conventional Commits: `type(scope): summary in the imperative`, in
English. Types: `feat`, `fix`, `docs`, `test`, `refactor`, `perf`, `build`, `ci`, `chore`.

**Pull request scope.** One topic per pull request.

**Tests.** Any change to specified behaviour comes with a conformance test. Any bug fix
comes with a test that fails without the fix. This applies to the gateway as well as the
SDKs.

## Reporting a vulnerability

Do not open a public issue. Follow [SECURITY.md](SECURITY.md).

## Code of conduct

Participation is governed by the [code of conduct](CODE_OF_CONDUCT.md). Reports:
hey@openfsp.org.

## License

Every contribution is published under the [Apache 2.0 license](LICENSE).
