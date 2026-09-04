# ERC-7540 Asynchronous Vault Conformance Review

[`workflow.json`](workflow.json) is an Open-Kritt export for reviewing production-
reachable asynchronous ERC-4626 vaults against ERC-7540. It is the source of truth
for the implemented prompts, schemas, step settings, and workflow metadata.

Workflow documentation version: `v0.1.0`. This version identifies the initial public
workflow release; no Git tag is implied.

## Current status

- Initial workflow implementation complete.
- Benchmarked against one historical audited implementation.
- Further benchmarks and iterative refinement are planned.
- Known improvement areas include cross-reviewer deduplication and severity
  calibration.

## Objective

The workflow maps each active ERC-7540 target, runs focused reviews of applicable
normative behavior, and adjudicates candidate deviations into evidence-backed final
findings. It covers ERC-20, ERC-165, ERC-4626, and ERC-7575 only where ERC-7540
explicitly requires, inherits, modifies, or relies on them.

## Scope

Review scope includes:

- ERC-7540 `MUST`, `MUST NOT`, relevant `SHOULD`, and clearly normative lifecycle
  behavior;
- Request -> Pending -> Claimable -> Claimed transitions;
- request IDs, aggregation, fungibility, and partial fulfillment;
- owner, controller, receiver, operator, caller, and allowance boundaries;
- ERC-4626 behavior overridden for asynchronous deposits or redemptions;
- required methods, overloads, getters, reverts, events, and interface declarations;
  and
- ERC-165 and ERC-7575 integration explicitly required by ERC-7540.

## Non-goals

This is not a general vault or protocol audit. The workflow excludes NAV and oracle
manipulation, strategy accounting, solvency and liquidity, epoch or protocol
economics, generic rounding, ERC-4626 inflation or donation attacks, generic
reentrancy, cancellation design, and arbitrary business logic unless the behavior
directly proves an applicable ERC-7540 violation.

It does not prescribe choices that ERC-7540 leaves open, such as a particular request
ID generator, settlement mechanism, exchange-rate formula, cancellation mechanism,
or ordering between distinct non-zero request IDs.

## Architecture

### Depth 0: target mapping

`Map Asynchronous Vault Targets` resolves production wiring, inheritance, proxies,
configuration, share-token relationships, entrypoints, state, authorization,
interfaces, events, and reachability. Its multi-output result contains zero to many
mapped targets, with one record per supported target. It does not make vulnerability
or conformance conclusions.

### Depth 1: focused review

Each mapped target is examined by six sibling reviewers:

1. `Review Flow, Interfaces and Standard Integration`
2. `Review Request Lifecycle and State Semantics`
3. `Review Request IDs, Aggregation and Partial Fulfillment`
4. `Review Owner, Controller and Operator Authorization`
5. `Review ERC-4626 Async Overrides and Claim Semantics`
6. `Review Methods, Getters, Reverts and Events`

Each reviewer emits zero to many structured candidate records, with one record per
materially distinct deviation it supports. Across all six multi-output siblings,
Depth 1 therefore produces a zero-to-many candidate batch. Candidates contain
requirement, configuration, source, trigger, impact, reachability, countercheck,
inheritance, and assumption evidence. Depth 1 does not assign final severity or force
a finding.

### Depth 2: batched adjudication

`Prove, Adjudicate and Classify ERC-7540 Findings` consumes the complete batch of
Depth 1 outputs. It reopens cited code, checks the exact normative rule and
applicability, resolves production paths and safeguards, rejects speculative or
permitted behavior, and deduplicates candidates sharing a root cause and materially
equivalent trigger.

The final multi-output step emits zero to many structured findings. A surviving
record includes a summary, proof-oriented explanation, primary path and line, trigger
flow, concrete input or transaction sequence, finding category, actor, and
exploitability flag. Zero records is a valid result at every multi-output stage;
placeholders are not required.

## Intended usage

Run the exported workflow in a compatible Open-Kritt installation against a pinned
repository commit and an explicit production scope. Preserve dependency and
configuration context. Review the map before relying on downstream coverage, then
manually reproduce and assess every final finding against the authoritative
[ERC-7540 specification](https://eips.ethereum.org/EIPS/eip-7540).

Use [`specification.md`](specification.md) to maintain the normative coverage map and
[`benchmark.md`](benchmark.md) to record evaluation evidence.

## Known limitations

- Coverage depends on correct target mapping and supplied production configuration.
- Static reasoning may miss runtime, proxy, deployment, or cross-contract behavior.
- Model and harness changes can change candidate quality and reproducibility.
- The final adjudicator considers candidates emitted at Depth 1; it is not a fresh
  general audit and may miss requirements that no sibling identifies.
- The workflow's narrow normative scope intentionally omits many material protocol
  and economic risks.
- `SHOULD` and other behavioral language can require contextual interpretation.

All candidates and findings require manual validation. Workflow output does not prove
complete ERC-7540 compliance and does not establish protocol security.

This is experimental open-source tooling. Standards conformance does not imply
economic or security correctness, and results can vary with the model, Open-Kritt
runtime, repository context, dependencies, and configuration.
