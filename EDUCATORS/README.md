# Educators — PYNTCLOUD

**Project:** PYNTCLOUD  
**Category:** VOXELIZATION  
**Upstream:** see BENCH.json  
**Pinned commit:** `8368c6a22f8060aeafacf2964276e8704d732145`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `5e313b667f303b7de14e36bb939205149ed95758e0f961b339559bab71d085fc`  
**Date:** October 2026

## Teaching with PYNTCLOUD

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `5e313b667f303b7de14e36bb939205149ed95758e0f961b339559bab71d085fc` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
