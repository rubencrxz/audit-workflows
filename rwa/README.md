# RWA and Tokenization Workflows

RWA and tokenization systems often compose several standards while adding explicit
roles and multi-step state transitions. A focused conformance review can make these
boundaries easier to inspect before a broader manual audit.

This collection emphasizes:

- role and permission semantics, including the authority of owners, controllers,
  operators, receivers and delegated callers.
- lifecycle requirements and the consistency of state transitions across requests,
  fulfillment and claims.
- interface declarations, required methods, observable return values, reverts and
  events.
- standards-aware security review where a concrete implementation behavior violates
  or undermines a normative requirement.

The workflows intentionally separate standards conformance from protocol economics
and general-purpose vulnerability discovery. Their output is review material, not a
certification: findings still require manual validation in the target's production
context.

## Available workflows

- [`ERC-7540 Asynchronous Vault Conformance Review`](erc-7540/)
- [`ERC-3643 Production Conformance Review`](erc-3643/)
