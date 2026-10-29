# AegisLoop — Evidence-Gated Infrastructure Recovery

AegisLoop is a Kestra workflow for evidence-driven incident assessment and controlled recovery planning.

## Features

- Scheduled service health probing.
- Deterministic incident diagnosis and recovery-action selection.
- Git-based runbook retrieval using `io.kestra.plugin.git.Clone`.
- Conditional routing and human approval before recovery.
- Allowlisted recovery actions and dry-run protection.
- Evidence artifacts and recovery-submission checks.

## Safety

**Dry-run mode is enabled by default.** The workflow must not be treated as proof of successful recovery: the tested approved path did not submit a recovery request. Real recovery requires separate validation of connectivity, authorization, and independent health verification.

## Configuration

Review the flow inputs before execution. For testing, use a reachable health endpoint, disable optional AI advice, set `dry_run` to `true`, and enable `approval_test_mode` only when testing the approval workflow.

The runbook repository input defaults to `https://github.com/kestra-io/blueprints`. Replace it with an appropriate operational runbook repository when available.

## Tested behavior

- Rejected approval blocks recovery submission.
- Approved dry-run records `status: dry_run` and `executed: false`.
- Git clone and runbook-search tasks completed in the local Kestra 2.0.4 test environment.

These results describe local tests; they do not establish that real recovery has been tested.
