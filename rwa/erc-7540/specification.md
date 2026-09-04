# ERC-7540 Coverage Map

This document maps concrete normative requirements to the workflow stages that
inspect and adjudicate them. The authoritative source is
[ERC-7540](https://eips.ethereum.org/EIPS/eip-7540). Add one row per independently
testable requirement; quote sparingly, link to the relevant specification section,
and record applicability separately for asynchronous deposits and redemptions.

Every candidate produced by a focused reviewer is ultimately subject to Depth 2,
`Prove, Adjudicate and Classify ERC-7540 Findings`.

Suggested status values: `mapped`, `partially mapped`, `not mapped`, and `not
applicable`.

## Flow / Interfaces / Standard Integration

Primary stage: `Review Flow, Interfaces and Standard Integration`.

| Requirement ID | Normative rule and class | Spec section | Applicability | Depth 0 evidence | Depth 1 checks | Test or proof reference | Status / notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| _TBD_ | _MUST / MUST NOT / SHOULD / normative behavior_ | _link_ | _deposits / redemptions / both_ | _symbols and wiring_ | _prompt/check_ | _test, trace, or evidence_ | _status_ |

## Request Lifecycle / State Semantics

Primary stage: `Review Request Lifecycle and State Semantics`.

| Requirement ID | Normative rule and class | Spec section | Applicability | Depth 0 evidence | Depth 1 checks | Test or proof reference | Status / notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| _TBD_ | _MUST / MUST NOT / SHOULD / normative behavior_ | _link_ | _deposits / redemptions / both_ | _state and transitions_ | _prompt/check_ | _test, trace, or evidence_ | _status_ |

## Request IDs / Fungibility / Partial Fulfillment

Primary stage: `Review Request IDs, Aggregation and Partial Fulfillment`.

| Requirement ID | Normative rule and class | Spec section | Applicability | Depth 0 evidence | Depth 1 checks | Test or proof reference | Status / notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| _TBD_ | _MUST / MUST NOT / SHOULD / normative behavior_ | _link_ | _ID zero / non-zero; deposits / redemptions_ | _ID and accounting state_ | _prompt/check_ | _multi-request trace or test_ | _status_ |

## Owner / Controller / Operator Authorization

Primary stage: `Review Owner, Controller and Operator Authorization`.

| Requirement ID | Normative rule and class | Spec section | Applicability | Depth 0 evidence | Depth 1 checks | Test or proof reference | Status / notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| _TBD_ | _MUST / MUST NOT / SHOULD / normative behavior_ | _link_ | _actor and flow_ | _authorization symbols_ | _prompt/check_ | _actor/call trace or test_ | _status_ |

## ERC-4626 Async Overrides / Claim Semantics

Primary stage: `Review ERC-4626 Async Overrides and Claim Semantics`.

| Requirement ID | Normative rule and class | Spec section | Applicability | Depth 0 evidence | Depth 1 checks | Test or proof reference | Status / notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| _TBD_ | _MUST / MUST NOT / SHOULD / normative behavior_ | _link_ | _async deposits / async redemptions_ | _overrides and dispatch_ | _prompt/check_ | _claim or preview test_ | _status_ |

## Methods / Getters / Reverts / Events

Primary stage: `Review Methods, Getters, Reverts and Events`.

| Requirement ID | Normative rule and class | Spec section | Applicability | Depth 0 evidence | Depth 1 checks | Test or proof reference | Status / notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| _TBD_ | _MUST / MUST NOT / SHOULD / normative behavior_ | _link_ | _method/event and flow_ | _method and event symbols_ | _prompt/check_ | _ABI, revert, or event test_ | _status_ |

## Cross-domain notes

Record overlaps here when one normative rule is intentionally checked by more than
one sibling. Identify the primary owner and the secondary backstop so overlap remains
useful without turning into duplicate final findings.

| Requirement ID | Primary reviewer | Secondary reviewer(s) | Deduplication guidance |
| --- | --- | --- | --- |
| _TBD_ | _stage_ | _stage(s)_ | _shared root cause and trigger guidance_ |
