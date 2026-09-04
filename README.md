# SmartnContract Audit Workflows

This repository collects reusable workflows for focused smart contract review. The
workflows are designed to help reviewers examine standards conformance,
authorization boundaries, lifecycle semantics, interface requirements and concrete
implementation deviations from normative behavior.

These workflows are first-pass review tools. They complement and do not replace,
manual security audits, protocol-specific threat modeling, economic analysis or
testing.

## Available workflows

| Area | Workflow | Version |
| --- | --- | --- |
| RWA / tokenization | [ERC-7540 Asynchronous Vault Conformance Review](rwa/erc-7540/) | `v0.1.0` |

## Repository layout

- [`rwa/`](rwa/) contains workflows for RWA and tokenization standards.
- [`rwa/erc-7540/`](rwa/erc-7540/) contains the ERC-7540 workflow, coverage map, and
  benchmark notes.
- [`templates/workflow-template.md`](templates/workflow-template.md) provides a
  practical outline for future standards-based workflows.

Contributions are welcome, including new workflows, tighter normative mappings,
benchmark evidence, false-positive reductions, and documentation improvements. Keep
claims evidence-based and distinguish standards conformance from broader protocol
security.

## Disclaimer

This repository contains experimental open source tooling. Every output requires
manual validation against the applicable specification, deployed configuration, and
production code. Standards conformance does not imply economic correctness or
protocol security, and workflow behavior can vary with the model, runtime, supplied
context, and configuration.
