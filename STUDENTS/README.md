# Students — PYNTCLOUD

**Project:** PYNTCLOUD  
**Category:** VOXELIZATION  
**Upstream:** see BENCH.json  
**Pinned commit:** `8368c6a22f8060aeafacf2964276e8704d732145`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `5e313b667f303b7de14e36bb939205149ed95758e0f961b339559bab71d085fc`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `8368c6a22f8060aeafacf2964276e8704d732145`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `5e313b667f303b7de14e36bb939205149ed95758e0f961b339559bab71d085fc`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
