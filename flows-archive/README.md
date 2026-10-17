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

## Archived 2026-10-17: extra templated copies on tools that have no stronger blueprint yet

Extra templated copies on tools that have no stronger blueprint yet. The best-scoring flow per tool is kept so the tool stays in the catalog. Moved as part of the catalog quality cleanup; any of them can come back once rewritten into a fuller, tested flow.

- `aerospike-namespace-device-high-watermark-and-eviction-sentinel`
- `apache-pinot-segment-unassigned-and-reload-sentinel`
- `apache-pulsar-bookie-journal-disk-exhaustion-sentinel`
- `api-health-contract-monitor`
- `argo-rollouts-analysisrun-metric-failure-sentinel`
- `aws-cloudwatch-log-group-retention-sentinel`
- `aws-ebs-unattached-volume-snapshot-and-prune`
- `aws-elasticache-engine-cpu-utilization-ceiling-guard`
- `aws-kms-key-rotation-disabled-sentinel`
- `aws-transit-gateway-attachment-packet-drop-sentinel`
- `aws-vpc-flow-logs-coverage-guard`
- `azure-aks-pending-pods-scheduling-deficit-sentinel`
- `azure-app-service-http-5xx-error-rate-sentinel`
- `azure-keyvault-certificate-expiration-countdown-notifier`
- `azure-sql-database-dtu-consumption-headroom-sentinel`
- `calico-felix-dataplane-programming-stall-and-route-drop-sentinel`
- `chromadb-collection-count-memory-guard-sentinel`
- `cilium-clustermesh-global-service-heartbeat-sentinel`
- `cilium-ebpf-map-capacity-overflow-and-bpf-tail-call-drop-sentinel`
- `consul-autopilot-dead-server-pruning-sentinel`
- `consul-kv-service-deregistration-sentinel`
- `consul-raft-leader-election-and-autopilot-health-sentinel`
- `consul-raft-leader-election-churn-and-heartbeat-sentinel`
- `consul-serf-membership-flap-and-health-check-failure-sentinel`
- `contour-ingress-httproute-status-conflict-sentinel`
- `contour-ingress-route-sync-error-and-xds-timeout-sentinel`
- `coredns-panics-and-restarts-health-sentinel`
- `coredns-upstream-plugin-servfail-and-cache-eviction-sentinel`
- `coredns-upstream-servfail-and-panics-sentinel`
- `cortex-tenant-sample-discard-and-querier-timeout-sentinel`
- `dapr-sidecar-actor-placement-table-lock-sentinel`
- `delta-lake-retry-safe-batch-load`
- `delta-lake-change-feed-sync`
- `dex-ldap-user-bind-timeout-sentinel`
- `dns-propagation-verifier`
- `dns-caa-issuer-policy-guard`
- `dnsmasq-lease-exhaustion-and-dhcp-ack-stall-sentinel`
- `dragonfly-cache-oom-drop-sentinel`
- `dragonfly-memory-saturation-and-eviction-sentinel`
- `dragonfly-replication-offset-drift-sentinel`
- `dragonfly-snapshot-save-lag-sentinel`
- `dragonfly-cluster-replication-offset-drift-sentinel`
- `dragonfly-dfdaemon-peer-upload-throughput-drop-sentinel`
- `dragonfly-p2p-peer-task-distribution-latency-sentinel`
- `ebs-unattached-volume-waste-detector`
- `emqx-cluster-shared-subscription-lag-and-session-eviction-sentinel`
- `envoy-proxy-cluster-circuit-breaker-overflow-sentinel`
- `envoy-access-log-service-als-drop-sentinel`
- `envoy-circuit-breaker-tripped-and-upstream-cx-connect-timeout-sentinel`
- `envoy-cluster-overflow-and-ejection-sentinel`
- `envoy-gateway-translator-route-conflict-sentinel`
- `envoy-wasm-filter-compilation-failure-sentinel`
- `falco-kernel-module-syscall-drop-rate-sentinel`
- `fluentbit-tail-input-buffer-full-and-disk-pause-sentinel`
- `github-branch-protection-compliance-sentinel`
- `glitchtip-unresolved-exception-spike-sentinel`
- `glusterfs-replicated-volume-split-brain-and-brick-offline-sentinel`
- `graphql-schema-compatibility-gate`
- `harbor-vulnerability-audit-scan-queue-stall-and-trivy-oom-sentinel`
- `hashicorp-consul-service-deregistration-sentinel`
- `hasura-graphql-engine-metadata-drift-sentinel`
- `kubernetes-coredns-nxdomain-rate-surge-sentinel`
- `kubernetes-mutating-webhook-configuration-failure-sentinel`
- `kubernetes-node-notready-condition-sentinel`
- `kubernetes-node-resource-pressure-sentinel`
- `kubernetes-orphaned-volume-finops-reclaimer`
- `kubernetes-pod-crashloopbackoff-sentinel`
- `kyverno-policy-violation-audit-and-admission-denial-sentinel`
- `linkerd-service-profile-retry-budget-exhaustion-sentinel`
- `litestream-sqlite-replication-lag-sentinel`
- `milvus-segment-growing-memory-headroom-sentinel`
- `milvus-memory-mmap-cache-utilization-sentinel`
- `neon-preview-branch-finops-pruner`
- `nomad-client-node-drain-status-sentinel`
- `nomad-job-allocation-client-drain-sentinel`
- `nomad-job-restart-backoff-failure-sentinel`
- `nomad-plan-allocation-blocked-evals-sentinel`
- `nomad-server-raft-leader-stability-sentinel`
- `nomad-allocation-reschedule-storm-guard`
- `nomad-client-allocation-oom-kill-and-drain-timeout-sentinel`
- `nomad-client-heartbeat-loss-sentinel`
- `openkruise-cloneset-rollout-update-stall-sentinel`
- `postmark-inbound-webhook-and-bounce-sentinel`
- `powerdns-authoritative-database-latency-and-packet-cache-sentinel`
- `razorpay-payment-failure-rate-sentinel`
- `razorpay-refund-stuck-sentinel`
- `razorpay-subscription-renewal-sentinel`
- `redpanda-under-replicated-partitions-and-cluster-health-sentinel`
- `redpanda-schema-id-exhaustion-and-validation-sentinel`
- `rook-nfs-export-mount-latency-and-client-disconnect-sentinel`
- `seaweedfs-filer-meta-dir-lookup-latency-sentinel`
- `seaweedfs-master-raft-leader-election-timeout-sentinel`
- `seaweedfs-volume-server-unassigned-chunk-sentinel`
- `thanos-compact-halted-overlap-sentinel`
- `thanos-compact-overlapped-blocks-sentinel`
- `thanos-query-frontend-cache-miss-ratio-sentinel`
- `thanos-query-frontend-split-latency-sentinel`
- `thanos-ruler-evaluation-missed-cycles-sentinel`
- `thanos-store-gateway-scan-failure-sentinel`
- `thanos-querier-engine-partial-response-warning-sentinel`
- `traefik-router-tls-certificate-expiration-and-retry-surge-sentinel`
- `trafficserver-remap-rule-reload-syntax-error-sentinel`
- `victoriametrics-high-cardinality-and-churn-sentinel`
- `victoriametrics-slow-queries-latency-sentinel`
- `victoriametrics-slow-queries-memory-pressure-sentinel`
- `victoriametrics-tsdb-retention-churn-and-slow-insert-sentinel`
- `victoriametrics-vmagent-scrape-target-drop-sentinel`
- `vpa-recommender-cgroup-oom-event-sentinel`
- `yugabytedb-under-replicated-tablets-and-raft-sentinel`
