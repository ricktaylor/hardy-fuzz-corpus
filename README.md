# hardy-fuzz-corpus

ClusterFuzzLite corpus storage for [hardy](https://github.com/ricktaylor/hardy)'s fuzz targets.

CFLite's git filestore reads and writes each fuzzer's corpus under `corpus/<fuzz_target>/`, so the layout here is:

```
corpus/
  decode/            cbor:decode
  eid_str/           bpv7:eid_str
  eid_cbor/          bpv7:eid_cbor
  random_bundles/    bpv7:random_bundles
  eid_pattern_str/   eid-patterns:eid_pattern_str
  bpa/               bpa:bpa
  passive/           tcpclv4:passive
  active/            tcpclv4:active
```

The `main` branch holds the corpus; CFLite publishes fuzzer coverage reports to the `gh-pages` branch (`coverage/`). Both are managed automatically by the `cflite-cron.yml` workflow in the hardy repo once the `PERSONAL_ACCESS_TOKEN` secret is configured. The initial corpus here was seeded from local fuzzing; CFLite's `prune` mode minimises it over time.
