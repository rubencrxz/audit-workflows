# ERC-7540 Workflow Benchmark: Lagoon v0

This file is a benchmark record, not an audit report. It documents one historical
comparison and leaves unmeasured fields explicit.

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

The benchmark ground truth is the public Nethermind audit of Lagoon v0. Lagoon
publishes reports through its
[public audits index](https://docs.lagoon.finance/resources/audits), which is the
public reference used for this benchmark record.

## Known historical findings

The supplied public-audit ground truth includes:

- **Critical:** a payable native deposit can record more assets than were actually
  provided; and
- **High:** settlement moves assets or shares belonging to newer requests that should
  remain Pending.

The audit also contains lower-severity or general protocol findings outside, or only
partially within, this workflow's narrow standards-conformance scope. This document
does not claim those findings as expected workflow coverage.

## Workflow-detected findings

Observed workflow results on the audited historical code included:

- deposit settlement consuming assets belonging to newer Pending requests;
- redemption settlement burning or consuming shares belonging to newer Pending
  requests; and
- a payable native deposit recording more assets than were actually custodied.

It also surfaced additional controller/claim authorization candidates and several
informational conformance candidates. Those additional results are unvalidated and
must not be treated as confirmed findings merely because the workflow emitted them.

## True positives

The payable native deposit result strongly corresponds to the known Critical finding.
The deposit and redemption settlement results strongly correspond to two
manifestations of the same known High finding. These are known issue matches for this
benchmark, but they do not establish general precision, recall, or performance on
other implementations.

## False positives

Not yet measured. In particular, the additional conformance and authorization
candidates require manual validation and must not be labeled findings solely because
the workflow emitted them.

## Missed findings

No complete in-scope missed-finding analysis has been recorded. Lower-severity and
general protocol findings that do not directly prove an ERC-7540 requirement
violation are intentional scope exclusions, not evidence of a workflow failure.
Findings that are only partially within scope still require case-by-case mapping
before being counted. No claim of complete in-scope coverage is made.

## Deduplication observations

The Depth 2 step consumes the full Depth 1 batch and is instructed to merge candidates
with the same root cause and materially equivalent trigger. In this run, the known
High appeared as separate deposit and redemption manifestations. Separate records can
be useful when triggers or effects differ, but the split shows that root-cause
grouping and cross-domain deduplication need further calibration. Measured pre/post
candidate counts have not been recorded.

## Severity observations

The final workflow schema records issue type and exploitability but does not emit a
severity field. Although the matched public findings were rated Critical and High by
Nethermind, the workflow does not independently reproduce those rankings. Severity
must be assigned manually from demonstrated impact, reachability, assumptions, and a
declared rubric; calibration remains an improvement area.

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
- The known matches have not yet been documented here with report IDs, source lines,
  or reproductions.
- No confusion matrix, repeated-run analysis, or coverage baseline is available.
- Additional candidates remain unvalidated, and missed in-scope findings have not
  been established.
- Results may depend on model, configuration, repository context, and workflow
  version.
- Matching known findings does not demonstrate complete ERC-7540 conformance or
  protocol security.
- More audited implementations and repeated runs are needed before drawing broader
  conclusions.
