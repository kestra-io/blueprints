# TL;DR: Sanity Checks in Kestra

Please check the [full Notion page](https://www.notion.so/kestra-io/Sanity-Checks-17c36907f7b58050ba65efe468e19011?pvs=4) for full information

Sanity checks in Kestra are test flows used to verify functionality of plugins and tasks:

**Structure:**

- Plugin sanity checks: Flow ID is the task name, namespace "sanitychecks", and include Assert tasks to test task outputs.
- Flow sanity checks: Flow ID mentions main tasks, namespace "sanitychecks", they tests complete workflow (always self-contained)

**External Dependencies:**

- OSS services: Use Docker Run/Stop tasks
- Cloud services: Leverage sandbox environments when possible
- SaaS/License services: Not currently supported (or hard coded credentials from demo accounts)

**Organization:**

- All sanity checks are synced to the blueprint repository
- Plugin checks: Located in plugin repos, pulled to blueprint repo via CI/CD
- Flow checks: Written directly in blueprint repo into the `sanitychecks/flows` folder. Blueprints with `demo: true` are also synced into `sanitychecks/flows/blueprints`


**Deployment:**

For now deploy to preview environment is done via GitSync flows (see Notion page).
Alternatively, you can upload through UI.