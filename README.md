<p align="center">
  <a href="https://www.kestra.io">
    <img src="https://kestra.io/banner.png"  alt="Kestra workflow orchestrator" />
  </a>
</p>

<h1 align="center" style="border-bottom: none">
    Event-Driven Declarative Orchestrator
</h1>

<div align="center">
 <a href="https://github.com/kestra-io/kestra/releases"><img src="https://img.shields.io/github/tag-pre/kestra-io/kestra.svg?color=blueviolet" alt="Last Version" /></a>
  <a href="https://github.com/kestra-io/kestra/blob/develop/LICENSE"><img src="https://img.shields.io/github/license/kestra-io/kestra?color=blueviolet" alt="License" /></a>
  <a href="https://github.com/kestra-io/kestra/stargazers"><img src="https://img.shields.io/github/stars/kestra-io/kestra?color=blueviolet&logo=github" alt="GitHub star" /></a> <br>
<a href="https://kestra.io"><img src="https://img.shields.io/badge/Website-kestra.io-192A4E?color=blueviolet" alt="Kestra infinitely scalable orchestration and scheduling platform"></a>
<a href="https://kestra.io/slack"><img src="https://img.shields.io/badge/Slack-Join%20Community-blueviolet?logo=slack" alt="Slack"></a>
</div>

<br />

<p align="center">
    <a href="https://twitter.com/kestra_io"><img height="25" src="https://kestra.io/twitter.svg" alt="twitter" /></a> &nbsp;
    <a href="https://www.linkedin.com/company/kestra/"><img height="25" src="https://kestra.io/linkedin.svg" alt="linkedin" /></a> &nbsp;
<a href="https://www.youtube.com/@kestra-io"><img height="25" src="https://kestra.io/youtube.svg" alt="youtube" /></a> &nbsp;
</p>

<p align="center">
    <a href="https://go.kestra.io/video/product-overview" target="_blank">
        <img src="https://kestra.io/startvideo.png" alt="Get started in 4 minutes with Kestra" width="640px" />
    </a>
</p>
<p align="center" style="color:grey;"><i>Get started with Kestra in 4 minutes.</i></p>

# Kestra Blueprints

The official Kestra Blueprints library can be found under [kestra.io/docs](https://kestra.io/blueprints).

Blueprints are a curated, organized, and searchable catalog of ready-to-use examples designed to help you kickstart your workflow.

Each Blueprint combines code and documentation and can be assigned several tags for organization and discoverability.

## Tutorial namespace

Some blueprints are packaged with Kestra and available in the `tutorial` namespace. This is a subset of the blueprints labeled "Getting Started".

## Contributing Tips

## Blueprint YAML contribution guidelines

When contributing Blueprints, please include clear metadata, documentation and runnable examples so other users can quickly understand, configure and run your flow.

Required & recommended fields
- `id` (required): hyphen-case, must match filename.
- `namespace` (required): owner/team namespace.
- `tasks` (required): fully-defined tasks; add `description` per task when behaviour isn't obvious.
- `extend` (required): use this metadata block to explain the Blueprint for the catalog UI.
  - `title`: concise human title (one line).
  - `description`: long explanation, prerequisites, steps to run, expected outputs, warnings.
  - `meta_description`: short summary (<= 160 chars) used for search/cards.
  - `tags`: categories to improve discoverability.
  - `ee`: true/false (Flows that require Enterprise Edition).
  - `demo`: true/false (mark runnable demo flows).

Documentation checklist for each blueprint
1. Prerequisites: list required secrets, services, images.
2. Secrets: list each secret name and exact purpose (do NOT include values).
3. Inputs: document each input (type, default, allowed values).
4. Outputs: show primary outputs and example paths (e.g., `{{ outputs.task.uri }}`).
5. Links: include links to plugin docs or external APIs used.

Style & best practices
- Keep `meta_description` short and searchable.
- Title should be human-friendly (not the same as id).
- Put examples for common pitfalls (e.g., enabling schedules, how to set secrets, expressions).
- Avoid hardcoding credentials — use `{{ secret('NAME') }}` placeholders.
- Add task-level `description` fields liberally to explain purpose and side-effects.
- Use `pluginDefaults` for API keys when the plugin supports it, and document the secret names.

Example `extend` template to copy-paste:
```yaml
extend:
  title: Short human-friendly title here
  description: |
    Short summary: what the Blueprint does.

    Prerequisites:
      - Secrets:
        - NAME: purpose (required)
      - Services: Redis, Postgres, SMTP, etc.
    Quick start:
      1. Set secrets
      2. Upload flow
      3. (Optional) Enable schedule and run
    Expected outputs:
      - outputs.my_task.uri: CSV file with results
  tags:
    - Getting Started # Check Blueprints page or other Blueprints for all possible tags
  ee: false
  demo: true
  meta_description: One-line summary suitable for search (<=160 chars)
```

Thank you for contributing — clear docs make Blueprints far more reusable, so be as detailed as you can :D

## Sanity checks

Sanity checks in Kestra are test flows used to verify functionality of plugins and tasks:

**Structure:**

- Plugin sanity checks: Flow ID is the task name, namespace "sanitychecks", and include Assert tasks to test task outputs.
- Flow sanity checks: Flow ID mentions main tasks, namespace "sanitychecks"; they test the complete workflow (always self-contained)

**External Dependencies:**

- OSS services: Use Docker Run/Stop tasks
- Cloud services: Leverage sandbox environments when possible
- SaaS/License services: Not currently supported (or hard-coded credentials from demo accounts)

**Organization:**

- All sanity checks are synced to the blueprint repository
- Plugin checks: Located in plugin repos, pulled to blueprint repo via CI/CD
- Flow checks: Written directly in blueprint repo into the `sanitychecks/flows` folder. Blueprints with `demo: true` are also synced into `sanitychecks/flows/blueprints`

Please check the [full Notion page](https://www.notion.so/kestra-io/Sanity-Checks-17c36907f7b58050ba65efe468e19011?pvs=4) for full information
