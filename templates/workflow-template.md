# Standards Workflow Template

Use this template to document a standards-based smart-contract review workflow. Keep
the executable workflow export as the source of truth and pin benchmark targets to
commits.

## Objective

State the concrete review objective, target implementation type, and expected use of
the results.

## Normative sources

List authoritative specifications and versions. Separate the primary standard from
standards that apply only through explicit inheritance, modification, or reliance.
Classify covered language (`MUST`, `MUST NOT`, relevant `SHOULD`, or other clearly
normative behavior).

## Scope

List the behaviors, interfaces, roles, state transitions, and integration boundaries
the workflow reviews.

## Exclusions

List protocol, economic, and generic security concerns that are out of scope. Explain
the narrow condition under which an excluded topic becomes relevant to a direct
standards violation.

## Mapping step

Define how the workflow discovers independently reviewable production targets and
resolves inheritance, libraries, proxies, factories, initialization, configuration,
and reachability. Specify the mapping output fields and zero-target behavior.

## Focused reviewers

For each review domain, record:

| Reviewer | Normative domain | Required inputs | Candidate evidence | Explicit non-scope |
| --- | --- | --- | --- | --- |
| _name_ | _requirements_ | _mapping fields_ | _source, path, trigger, impact, counterchecks_ | _excluded checks_ |

State whether reviewers run as siblings and confirm that each may emit zero to many
candidates without manufacturing placeholders.

## Adjudication / proof stage

Define how candidates are batched, independently verified, checked for applicability
and production reachability, deduplicated, rejected when speculative or permitted,
and promoted to final findings. State that unresolved necessary assumptions result in
rejection or an explicit non-finding status.

## Output schema

Document mapping, candidate, and final finding schemas. For each field, specify its
type, meaning, required evidence, and whether it is machine-consumed. Record
multi-output and consume-all settings.

| Stage | Field | Type | Meaning / evidence requirement |
| --- | --- | --- | --- |
| _stage_ | _field_ | _type_ | _definition_ |

## Benchmark methodology

Record:

- public target repository and pinned audited/fixed commits;
- public audit or issue references;
- in-scope known findings and the matching rule;
- model, harness, workflow hash, configuration, and run count;
- validation procedure and true-positive criteria;
- false positives, missed findings, and exclusions;
- candidates before and after adjudication/deduplication; and
- severity rubric and any disagreements.

Do not infer recall, precision, or general effectiveness from isolated examples.

## Limitations

Describe mapping, static-analysis, model, configuration, reproducibility, scope, and
benchmark limitations. Require manual validation and state plainly that the workflow
does not certify standards compliance or replace a security audit.
