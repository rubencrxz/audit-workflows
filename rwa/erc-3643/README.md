# ERC-3643 Production Conformance Review

[`workflow.json`](workflow.json) is an Open-Kritt export for structured first-pass
analysis of production-reachable ERC-3643 implementations. It is the source of truth
for the prompts, schemas, step settings and workflow metadata.

Workflow documentation version: `v0.1.0`. This version identifies the initial public
workflow release; no Git tag is implied.

## Purpose and scope

The workflow reviews official `MUST` and `MUST NOT` requirements, other binding
behavior and official interface obligations applicable to an ERC-3643 system. Its
authoritative starting point is the
[ERC-3643 specification](https://eips.ethereum.org/EIPS/eip-3643), together with
the ERC-20, ERC-173 and ONCHAINID interfaces that the specification directly
references.

The review applies Solidity and ABI compatibility rules. It evaluates externally
observable selectors, types, mutability, event signatures and behavior without
requiring identical source syntax, parameter names or declaration order.

## Architecture

The nine-step workflow has four depths:

1. **Depth 0 — normative catalogue:** builds one shared catalogue of atomic,
   source-anchored obligations from official sources.
2. **Depth 1 — production mapping:** maps production-reachable ERC-3643 components
   and routes applicable catalogue requirements to each component.
3. **Depth 2 — six focused reviewers:** examines transfers and ERC-20 behavior;
   identity, claims and registries; compliance and callbacks; privileged token
   operations; recovery, freeze and pause controls; and roles, interfaces and batch
   variants.
4. **Depth 3 — adjudication:** independently checks, deduplicates and promotes only
   supported conformance deviations to final findings.

## Exclusions

This workflow is not a general security, economic, governance, legal or
regulatory-policy audit. Those topics are considered only when they directly
establish or disprove an applicable official ERC-3643 obligation. It does not treat
reference-implementation choices or common hardening practices as normative rules.

## Intended usage and limitations

Run the workflow against a pinned repository revision with explicit production scope,
dependencies and configuration. Manually verify the catalogue, mapping and every
reported deviation against the official specification and the active implementation.

Coverage depends on source availability, production mapping, proxy and deployment
context, supplied configuration and model behavior. Zero final findings does not
establish complete ERC-3643 compliance, and professional auditor review remains
required.

Use [`specification.md`](specification.md) to maintain the normative coverage map and
[`benchmark.md`](benchmark.md) to record reproducible evaluation evidence.
