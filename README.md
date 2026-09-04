# Smart-Contract Audit Workflows

This repository collects reusable workflows for focused smart-contract review. The
workflows are designed to help reviewers examine standards conformance,
authorization boundaries, lifecycle semantics, interface requirements, and concrete
implementation deviations from normative behavior.

The initial collection focuses on real-world asset (RWA) and tokenization standards.
The first workflow reviews asynchronous ERC-4626 vaults against ERC-7540.

These workflows are first-pass review tools. They complement, and do not replace,
manual security audits, protocol-specific threat modeling, economic analysis, or
testing. Every emitted candidate or finding must be validated by a qualified reviewer
against the applicable specification, deployed configuration, and production code.

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
