# ERC-7540 Workflow Benchmark: Lagoon v0

This file is a benchmark record, not an audit report. It documents the currently
supplied comparison facts and leaves unmeasured fields explicit.

## Target repository

- Repository: [hopperlabsxyz/lagoon-v0](https://github.com/hopperlabsxyz/lagoon-v0)
- Target: the historical Lagoon v0 ERC-7540 implementation

## Audited commit

Nethermind audited commit:
[`090461aff6aca5f42f3013a51679c62ed9fe78c3`](https://github.com/hopperlabsxyz/lagoon-v0/commit/090461aff6aca5f42f3013a51679c62ed9fe78c3)

## Fixed commit

Final fixed commit:
[`cd6135f5b948b5b6c32abfc2201bd2d1b96221f4`](https://github.com/hopperlabsxyz/lagoon-v0/commit/cd6135f5b948b5b6c32abfc2201bd2d1b96221f4)

## Public audit reference

The benchmark context identifies the relevant public audit as Nethermind's Lagoon v0
audit. Lagoon publishes reports through its
[public audits index](https://docs.lagoon.finance/resources/audits). The exact report
file corresponding to the supplied commit has not yet been recorded here; add the
direct report URL after verifying its metadata.

## Known historical findings

The supplied benchmark context identifies these historical issues:

- settlement could consume newer Pending deposit or redemption requests; and
- a payable native deposit path could account for more assets than were actually
  custodied.

This scaffold does not independently restate their original titles, severities,
affected lines, or remediation details.

## Workflow-detected findings

The workflow surfaced observations strongly matching both historical issues above:

- settlement consuming newer Pending deposit/redemption requests; and
- payable native deposit accounting more assets than actually custodied.

It also surfaced additional ERC-7540 conformance and authorization candidates. Those
candidates have not yet been manually classified in this benchmark.

## True positives

Two workflow results are strong matches to supplied descriptions of known public
findings. Treat them as provisional true positives until a reviewer records a
line-by-line comparison with the public report and audited commit. No broader recall
or precision conclusion is supported yet.

## False positives

Not yet measured. In particular, the additional conformance and authorization
candidates require manual validation and must not be labeled findings solely because
the workflow emitted them.

## Missed findings

Not yet measured. The supplied facts do not establish the complete applicable audit
finding set or which findings fall within this workflow's deliberately narrow
ERC-7540 scope.

## Deduplication observations

The Depth 2 step consumes all Depth 1 candidates and is instructed to merge candidates
with the same root cause and materially equivalent trigger. No measured pre/post
deduplication counts or quality conclusions have been supplied.

## Severity observations

Not yet measured. The final workflow schema records issue type and exploitability but
does not emit a severity field. Severity should be assigned manually from demonstrated
impact, reachability, and the benchmark's chosen rubric.

## Model / configuration

Not recorded in the supplied benchmark context. Future runs should record at least:

- Open-Kritt version and workflow export hash;
- model provider, model identifier, and relevant inference settings;
- repository scope, dependencies, and configuration supplied to the run;
- number of runs and whether results were deterministic; and
- any manual context, exclusions, or post-processing.

## Limitations

- This is one historical implementation and two supplied issue matches, not a
  representative benchmark suite.
- The two matches have not yet been documented with report IDs, source lines, or
  reproductions in this file.
- No confusion matrix, repeated-run analysis, or coverage baseline is available.
- Additional candidates remain unvalidated, and missed in-scope findings have not
  been established.
- Results may depend on model, configuration, repository context, and workflow
  version.
- Matching known findings does not demonstrate complete ERC-7540 conformance or
  protocol security.
