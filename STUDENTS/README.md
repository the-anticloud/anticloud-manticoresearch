# Students — MANTICORESEARCH

**Project:** MANTICORESEARCH  
**Category:** SEARCH_ENGINES  
**Upstream:** see BENCH.json  
**Pinned commit:** `448a133e561ba90fa027c838bbec6353c6780847`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `36fd8ae6d2229a395bda869e9706a6a58b1075dd1d19055de084d8564825f116`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `448a133e561ba90fa027c838bbec6353c6780847`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `36fd8ae6d2229a395bda869e9706a6a58b1075dd1d19055de084d8564825f116`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
