---
name: "Blueprint PR checklist"
about: "Confirm your blueprint PR includes all required metadata and docs from the README"
title: "[Blueprint] <flow id> – PR checklist"
labels: ["blueprint"]
---

## Required metadata
- [ ] `id` matches the filename (hyphen-case) and `namespace` is set.
- [ ] `tasks` are fully defined; add `description` where behaviour is not obvious.
- [ ] `extend` block includes: `title`, rich `description` (prerequisites, quick start, expected outputs), `meta_description` (<=160 chars), `tags`, `ee`, and `demo`.

## Documentation checklist
- [ ] Prerequisites are listed (services/images) and every secret is named with its purpose (no values).
- [ ] Inputs are documented (type, defaults, allowed values) and primary outputs include example paths (e.g., `{{ outputs.task.uri }}`).
- [ ] Links to plugin docs and external APIs are included.

## Best practices
- [ ] No hardcoded credentials; use `{{ secret('NAME') }}` or plugin defaults.
- [ ] Added examples or notes for common pitfalls (schedules, secret setup, expressions) when relevant.
