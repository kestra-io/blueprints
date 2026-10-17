# Archived blueprints

Blueprints moved out of `flows/` because they fall outside the catalog's scope: a business or accounting calculation over a table with a notification at the end, rather than orchestration of a real system.

Files here are not indexed and do not appear on kestra.io/blueprints. They are kept so any of them can be reworked into a broader, integration-driven version and moved back.

## Archived 2026-10-17: flows that fake their data

These flows replace the real system's response with hard-coded or "simulated" values when the call fails (or always), so they report healthy without seeing the system. They are kept here for reference and can be restored once rewritten to fail loudly instead.

- `cilium-bpf-map-pressure-and-drop-sentinel`
- `cloud-iam-key-rotation-hygiene-sentinel`
- `coredns-upstream-servfail-and-latency-sentinel`
- `delta-checkpoint-staleness-and-log-bloat-sentinel`
- `fluent-bit-storage-buffer-and-retry-failure-sentinel`
- `harbor-project-storage-quota-and-scanner-sentinel`
- `jaeger-trace-spans-dropped-and-storage-error-sentinel`
- `kong-upstream-target-health-and-balancer-sentinel`
- `milvus-collection-index-state-and-unindexed-entity-sentinel`
- `minio-cluster-disk-healing-sentinel`
- `pgbouncer-client-wait-and-pool-exhaustion-sentinel`
- `proxysql-hostgroup-shunned-server-and-latency-sentinel`
- `tempo-ingester-span-drop-and-compact-sentinel`
- `thanos-compact-halted-and-overlap-sentinel`
- `traefik-http-router-and-service-health-sentinel`
- `trino-worker-spill-and-memory-headroom-sentinel`
- `valkey-cluster-slot-coverage-and-migration-sentinel`
- `zookeeper-ensemble-quorum-and-latency-sentinel`
