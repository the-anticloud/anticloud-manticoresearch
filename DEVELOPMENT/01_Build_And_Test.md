# Build and Test

**Project:** `MANTICORESEARCH`
**Upstream:** https://github.com/manticoresoftware/manticoresearch
**License:** GPL

## Quick Start

```bash
git clone https://github.com/manticoresoftware/manticoresearch
cd manticoresearch
pip install -r requirements-anticloud.txt
python anticloud_main.py --offline --pax-local
```

## Anticloud Improvements Applied

1. PAX L5 Narrow L2 General 27B local semantic search — no third-party embedding API
2. AIOSS append-only index change log for reproducible search results
3. AES-256 encryption for all indexed private documents
4. Single-binary search engine deployable on single server
5. Zero-cloud: all crawling, indexing, and ranking runs locally
6. GPU/CPU equalizer: dense retrieval on GPU, BM25 on CPU
7. Zero-telemetry: no query logging to third parties
8. Open search API: OpenSearch-compatible REST interface

## Benchmark Targets

| Metric | Target |
| --- | --- |
| Latency | Primary inference task: <5s on CPU, <1s on GPU |
| Throughput | Batch processing: >100 items/hour on single CPU server |
| Memory | <8GB RAM for standard deployment |
| Accuracy | Task-specific accuracy within 5% of cloud-API baseline |

## Build Status

Not yet measured. Run verified build and record actual figures above.
