# Ethics — MANTICORESEARCH

**Project:** MANTICORESEARCH  
**Category:** SEARCH_ENGINES  
**Upstream:** see BENCH.json  
**Pinned commit:** `448a133e561ba90fa027c838bbec6353c6780847`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `36fd8ae6d2229a395bda869e9706a6a58b1075dd1d19055de084d8564825f116`  
**Date:** October 2026

## Position

MANTICORESEARCH is packaged for offline deployment with a verifiable audit trail. The
ethical questions this raises are answered by making the system's behaviour
checkable rather than by policy statements.

## The four commitments

1. **No hidden egress.** The deployment has no external API dependency; this is
   testable by running it with the network disconnected.
2. **Attributable output.** Every artifact is recorded in a hash chain, so what
   the system produced can be reconstructed.
3. **Operator control.** The institution owns the hardware and the keys.
4. **Refusal to overclaim.** Where a certification is not held, the project says
   so rather than implying it.

## Dual use

This project is packaged for civilian and public-sector deployment. Where an
upstream has dual-use characteristics, the licence gate and the reference-only
marking in `BENCH.json` record that.
