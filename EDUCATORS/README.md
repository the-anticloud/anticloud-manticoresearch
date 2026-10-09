# Educators — MANTICORESEARCH

**Project:** MANTICORESEARCH  
**Category:** SEARCH_ENGINES  
**Upstream:** see BENCH.json  
**Pinned commit:** `448a133e561ba90fa027c838bbec6353c6780847`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `36fd8ae6d2229a395bda869e9706a6a58b1075dd1d19055de084d8564825f116`  
**Date:** October 2026

## Teaching with MANTICORESEARCH

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `36fd8ae6d2229a395bda869e9706a6a58b1075dd1d19055de084d8564825f116` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
