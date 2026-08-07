# Verification Results for PR #261 (source-backed-company-enrichment.yaml)

## 1. Task Assertion Verification

```
tasks: ['enrich_company', 'get_source_backed_result', 'verify_source_backed_result', 'log_audit_receipt', 'write_json', 'reshape', 'to_csv', 'create_table', 'load_data']
```

- `verify_source_backed_result` is present and unchanged.
- Total tasks: 9 (>= 6 required downstream tasks present).

## 2. Plugin Existence Proof

```
io.kestra.plugin.apify.actor.Run -> aparece em 4 outro(s) flow(s)
io.kestra.plugin.apify.dataset.Get -> aparece em 4 outro(s) flow(s)
io.kestra.plugin.core.execution.Assert -> aparece em 7 outro(s) flow(s)
io.kestra.plugin.core.log.Log -> aparece em 102 outro(s) flow(s)
io.kestra.plugin.core.storage.Write -> aparece em 10 outro(s) flow(s)
io.kestra.plugin.graalvm.python.FileTransform -> aparece em 2 outro(s) flow(s)
io.kestra.plugin.jdbc.postgresql.CopyIn -> aparece em 6 outro(s) flow(s)
io.kestra.plugin.jdbc.postgresql.Query -> aparece em 13 outro(s) flow(s)
io.kestra.plugin.serdes.csv.IonToCsv -> aparece em 24 outro(s) flow(s)
```

All 9 plugin types exist in multiple other flows across the repository (0 plugins with 0 occurrences).
