# AegisLoop architecture and safety invariants

## Components

1. **Probe:** performs one HTTP GET, enforces URL scheme and timeout limits, and records observed response status and latency.
2. **Deterministic diagnosis:** maps the observation to `healthy`, `warning`, or `critical` and proposes at most one allowlisted demo action.
3. **Optional local AI advisor:** sends a redacted evidence object to a loopback-only OpenAI-compatible endpoint. AI text is advisory and is never parsed as an executable action.
4. **Kestra policy branch:** healthy and dry-run paths do not reach the executor. A non-dry-run action enters `Pause`.
5. **Recovery gateway executor:** after manual resume, validates the action and loopback URL and makes one bounded POST. It never invokes shell commands.
6. **Evidence artifacts:** JSON outputs preserve the observed evidence, decision, AI status, approval state, and gateway response.

## Invariants

- AI output must not modify `severity`, `proposed_action`, `allowed_actions`, `dry_run`, or the approval requirement.
- A missing or invalid health response is not healthy.
- No action is sent unless the execution was manually resumed, `dry_run` is false, the action is allowlisted, and the gateway URL is credential-free loopback HTTP.
- No retries are performed for recovery actions.
- A gateway HTTP success is only `submitted`, not `recovery_verified`.
- The default path is read-only.

## Threat model

**In scope:** transient service failure, malformed endpoint values, remote AI endpoint misuse, unapproved or unknown action, accidental production URL configuration, and false-positive recovery claims.

**Mitigations:** strict URL parsing, loopback-only AI and recovery endpoints, action allowlist, timeouts, bounded response reads, explicit human pause, dry-run default, no shell calls, and explicit evidence state.

**Out of scope:** compromised Kestra administrators, a malicious local inference server, host compromise, production IAM design, and service-specific transactional rollback. Production use requires service-specific authentication, network policy, authorization, durable audit storage, and independent verification.
