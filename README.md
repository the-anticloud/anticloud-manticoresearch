# MANTICORESEARCH

![license](https://img.shields.io/badge/license-license-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-search_engines-lightgrey)

> Anticloud-hardened packaging of the upstream project `MANTICORESEARCH` in category **SEARCH ENGINES**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** SEARCH ENGINES · **Upstream:** https://github.com/manticoresoftware/manticoresearch-php · **Upstream pin:** `448a133e561ba90fa027c838bbec6353c6780847` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

<p align="center">
  <a href="https://manticoresearch.com" target="_blank" rel="noopener">
    <img src="https://manticoresearch.com/logo.png" width="50%" alt="Manticore Search Logo">
  </a>
</p>

<h3 align="center"><strong>Easy to use open source fast database for search</strong></h3>
<p align="center">
Manticore Search is an easy-to-use, open-source, and fast database designed for search. It is a great alternative to Elasticsearch.
</p>

<div align="center">
<a href="https://trendshift.io/projects/3537" target="_blank"><img src="https://trendshift.io/api/badge/projects/3537" alt="manticoresoftware%2Fmanticoresearch | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>
</div>

<h3 align="center">
  <a href="https://manticoresearch.com">Website</a> •
  <a href="https://manticoresearch.com/install/">Downloads</a> •
  <a href="https://manual.manticoresearch.com">Docs</a> •
  <a href="https://manticoresearch.com/blog/">Blog</a> •
  <a href="https://play.manticoresearch.com">Courses</a> •
  <a href="https://forum.manticoresearch.com">Forum</a> •
  <a href="https://slack.manticoresearch.com">Slack</a> •
  <a href="https://t.me/manticoresearch_en">Telegram (En)</a> •
  <a href="https://t.me/manticore_chat">Telegram (Ru)</a> •
  <a href="https://twitter.com/manticoresearch">Twitter</a> •
  <a href="https://github.com/manticoresoftware/manticoresearch/discussions/categories/feedback">User feedback</a>
</h3>

<p align="center">
<a href="LICENSE"><img alt="License: GPLv3 or later" src="https://img.shields.io/badge/license-GPL%20V3%2B-green?style=plastic"></a>
<a href="https://github.com/manticoresoftware/manticoresearch/actions/workflows/test.yml?query=branch%3Amain"><img alt="GitHub Actions Workflow Status" src="https://img.shields.io/github/actions/workflow/status/manticoresoftware/manticoresearch/test.yml?branch=main&style=plastic&color=green"></a>
<a href="https://twitter.com/manticoresearch"><img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/manticoresearch?color=green&logo=Twitter&style=plastic"></a>
<a href="http://slack.manticoresearch.com/"><img alt="Slack" src="https://img.shields.io/badge/slack-manticoresearch-green.svg?logo=slack&style=plastic"></a>
<a href="https://github.com/manticoresoftware/docker"><img alt="Docker pulls" src="https://img.shields.io/docker/pulls/manticoresearch/manticore?color=green&style=plastic"></a>
<a href="https://eepurl.com/dkUTHv"><img alt="Newsletter" src="https://img.shields.io/badge/newsletter-green?style=plastic"></a>
<a href="https://github.com/manticoresoftware/manticoresearch/graphs/commit-activity"><img alt="Activity" src="https://img.shields.io/github/commit-activity/m/manticoresoftware/manticoresearch?color=green&style=plastic"></a>
<a href="https://github.com/manticoresoftware/manticoresearch/issues?q=is%3Aissue+is%3Aclosed"><img alt="GitHub closed issues" src="https://img.shields.io/github/issues-closed/manticoresoftware/manticoresearch?color=green&style=plastic"></a>
</p>

# Introduction

What distinguishes Manticore from other solutions is:
* It's very fast and therefore more cost-efficient than alternatives. In the current [reproducible benchmarks](https://github.com/db-benchmarks/db-benchmarks), Manticore Search 27.1.5 is:
  - [**340x faster** than MySQL 9.7.1](https://db-benchmarks.com/?cache=fast_avg&engines=manticoresearch_27.1.5%2Cmysql_9.7.1&tests=hn_small&memory=110000) and [**6.51x faster** than Typesense 27.1](https://db-benchmarks.com/?cache=fast_avg&engines=manticoresearch_27.1.5%2Ctypesense_27.1&tests=hn_small&memory=110000) for 1.1M Hacker News comments
  - **3.85x faster** than tuned Elasticsearch 9.4.3 for [100M+ Hacker News comments](https://db-benchmarks.com/?cache=fast_avg&engines=manticoresearch_rowwise_27.1.5%2Celasticsearch_tuned_9.4.3&tests=hn&memory=110000)
  - [**5.03x faster** than tuned Elasticsearch 9.4.3](https://db-benchmarks.com/?cache=fast_avg&engines=elasticsearch_tuned_9.4.3%2Cmanticoresearch_columnar_27.1.5&tests=logs10m&memory=110000&queries=0%2C1%2C3%2C4%2C10%2C11) for selected typical DevOps queries on 10M Nginx logs; [**1.71x faster** than ClickHouse 26.6.1.1193](https://db-benchmarks.com/?cache=fast_avg&engines=manticoresearch_columnar_27.1.5%2Cclickhouse_26.6.1.1193&tests=logs10m&memory=110000) across the dashboard's default 10M-log query selection
  - [**2.02x faster** than tuned Elasticsearch 9.4.3](https://db-benchmarks.com/?cache=fast_avg&engines=manticoresearch_columnar_27.1.5%2Celasticsearch_tuned_9.4.3&tests=taxi&memory=110000) and [**3.16x faster** than ClickHouse 26.6.1.1193](https://db-benchmarks.com/?cache=fast_avg&engines=manticoresearch_columnar_27.1.5%2Cclickhouse_26.6.1.1193&tests=taxi&memory=110000) for 1.7B NYC taxi rides
  - For the same [10M Nginx-log ingestion](https://db-benchmarks.com/?cache=fast_avg&engines=elasticsearch_tuned_9.4.3%2Cmanticoresearch_columnar_27.1.5&tests=logs10m&memory=110000&queries=0%2C1%2C3%2C4%2C10%2C11), Manticore Search Columnar 27.1.5 completed in **5m 46s** vs **10m 15s** for tuned Elasticsearch 9.4.3, using **1.02 vs 3.80 CPU cores** on average, **3.98 GB vs 36.98 GB RAM** on average, and **0.41 MB read / 8.05 GB written** vs **322.14 MB read / 18.47 GB written**.

  Results are workload-specific; use the linked dashboard to select the queries that match your workload.
* ⚡ **Multi-threaded query execution** and efficient query parallelization use all CPU cores for low response times.
* 🔎 **Full-text search** works seamlessly with both small and large datasets.
* 🧩 **Hybrid search** combines full-text and vector retrieval in a single query for better relevance.
* 🧠 **Auto-embeddings with automatic chunking** generate vectors from text and can [split long documents](https://manual.manticoresearch.com/Searching/KNN#Chunking-strategies) into fixed-size, recursive, or sentence-based chunks stored in a `float_vector_array`, making relevant sections searchable without application-side chunking.
* 💬 **Conversati

*(excerpt; full text in `UPSTREAM_CLONE/`)*

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **C/C++ / CMake** (manifests: CMakeLists.txt, configure; scanned in UPSTREAM_CLONE)
- Top-level source layout: `actions/`, `api/`, `cmake/`, `component-licenses/`, `config/`, `contrib/`, `dist/`, `doc/`, `galera_packaging/`, `libicu/`, `libre2/`, `libstemmer_c/`
- Snapshot size: **2546 files**, **344971 lines of code** (measured; see Benchmarks)
- Primary languages: `.md` (596), `.rec` (376), `.h` (375), `.cpp` (316), `.xml` (165), `.bin` (139)
- Upstream commit pinned for this packaging: `448a133e561ba90fa027c838bbec6353c6780847`

---

## Installation

<a href="https://manual.manticoresearch.com">Docs</a> •
  <a href="https://manticoresearch.com/blog/">Blog</a> •
  <a href="https://play.manticoresearch.com">Courses</a> •
  <a href="https://forum.manticoresearch.com">Forum</a> •
  <a href="https://slack.manticoresearch.com">Slack</a> •
  <a href="https://t.me/manticoresearch_en">Telegram (En)</a> •
  <a href="https://t.me/manticore_chat">Telegram (Ru)</a> •
  <a href="https://twitter.com/manticoresearch">Twitter</a> •
  <a href="https://github.com/manticoresoftware/manticoresearch/discussions/categories/feedback">User feedback</a>
</h3>

<p align="center">
<a href="LICENSE"><img alt="License: GPLv3 or later" src="https://img.shields.io/badge/license-GPL%20V3%2B-green?style=plastic"></a>
<a href="https://github.com/manticoresoftware/manticoresearch/actions/workflows/test.yml?query=branch%3Amain"><img alt="GitHub Actions Workflow Status" src="https://img.shields.io/github/actions/workflow/status/manticoresoftware/manticoresearch/test.yml?branch=main&style=plastic&color=green"></a>
<a href="https://twitter.com/manticoresearch"><img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/manticoresearch?color=green&logo=Twitter&style=plastic"></a>
<a href="http://slack.manticoresearch.com/"><img alt="Slack" src="https://img.shields.io/badge/slack-manticoresearch-green.svg?logo=slack&style=plastic"></a>
<a href="https://github.com/manticoresoftware/docker"><img alt="Docker pulls" src="https://img.shields.io/docker/pulls/manticoresearch/manticore?color=green&style=plastic"></a>
<a href="https://eepurl.com/dkUTHv"><img alt="Newsletter" src="https://img.shields.io/badge/newsletter-green?style=plastic"></a>
<a href="https://github.com/manticoresoftware/manticoresearch/graphs/commit-activity"><img alt="Activity" src="https://img.shields.io/github/commit-activity/m/manticoresoftware/manticoresearch?color=green&style=plastic"></a>
<a href="https://github.com/manticoresoftware/manticoresearch/issues?q=is%3Aissue+is%3Aclosed"><img alt="GitHub closed issues" src="https://img.shields.io/github/issues-closed/manticoresoftware/manticoresearch?color=green&style=plastic"></a>
</p>

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

<p align="center">
Manticore Search is an easy-to-use, open-source, and fast database designed for search. It is a great alternative to Elasticsearch.
</p>

<div align="center">
<a href="https://trendshift.io/projects/3537" target="_blank"><img src="https://trendshift.io/api/badge/projects/3537" alt="manticoresoftware%2Fmanticoresearch | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>
</div>

<h3 align="center">
  <a href="https://manticoresearch.com">Website</a> •
  <a href="https://manticoresearch.com/install/">Downloads</a> •
  <a href="https://manual.manticoresearch.com">Docs</a> •
  <a href="https://manticoresearch.com/blog/">Blog</a> •
  <a href="https://play.manticoresearch.com">Courses</a> •
  <a href="https://forum.manticoresearch.com">Forum</a> •
  <a href="https://slack.manticoresearch.com">Slack</a> •
  <a href="https://t.me/manticoresearch_en">Telegram (En)</a> •
  <a href="https://t.me/manticore_chat">Telegram (Ru)</a> •
  <a href="https://twitter.com/manticoresearch">Twitter</a> •
  <a href="https://github.com/manticoresoftware/manticoresearch/discussions/categories/feedback">User feedback</a>
</h3>

<p align="center">
<a href="LICENSE"><img alt="License: GPLv3 or later" src="https://img.shields.io/badge/license-GPL%20V3%2B-green?style=plastic"></a>
<a href="https://github.com/manticoresoftware/manticoresearch/actions/workflows/test.yml?query=branch%3Amain"><img alt="GitHub Actions Workflow Status" src="https://img.shields.io/github/actions/workflow/status/manticoresoftware/manticoresearch/test.yml?branch=main&style=plastic&color=green"></a>
<a href="https://twitter.com/manticoresearch"><img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/manticoresearch?color=green&logo=Twitter&style=plastic"></a>
<a href="http://slack.manticoresearch.com/"><img alt="Slack" src="https://img.shields.io/badge/slack-manticoresearch-green.svg?logo=slack&style=plastic"></a>
<a href="https://github.com/manticoresoftware/docker"><img alt="Docker pulls" src="https://img.shields.io/docker/pulls/manticoresearch/manticore?color=green&style=plastic"></a>
<a href="https://eepurl.com/dkUTHv"><img alt="Newsletter" src="https://img.shields.io/badge/newsletter-green?style=plastic"></a>
<a href="https://github.com/manticoresoftware/manticoresearch/graphs/commit-activity"><img alt="Activity" src="https://img.shields.io/github/commit-activity/m/manticoresoftware/manticoresearch?color=green&style=plastic"></a>
<a href="https://github.com/manticoresoftware/manticoresearch/issues?q=is%3Aissue+is%3Aclosed"><img alt="GitHub closed issues" src="https://img.shields.io/github/issues-closed/manticoresoftware/manticoresearch?color=green&style=plastic"></a>
</p>

*Section quoted from the upstream readme.*
Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

</div>

<h3 align="center">
  <a href="https://manticoresearch.com">Website</a> •
  <a href="https://manticoresearch.com/install/">Downloads</a> •
  <a href="https://manual.manticoresearch.com">Docs</a> •
  <a href="https://manticoresearch.com/blog/">Blog</a> •
  <a href="https://play.manticoresearch.com">Courses</a> •
  <a href="https://forum.manticoresearch.com">Forum</a> •
  <a href="https://slack.manticoresearch.com">Slack</a> •
  <a href="https://t.me/manticoresearch_en">Telegram (En)</a> •
  <a href="https://t.me/manticore_chat">Telegram (Ru)</a> •
  <a href="https://twitter.com/manticoresearch">Twitter</a> •
  <a href="https://github.com/manticoresoftware/manticoresearch/discussions/categories/feedback">User feedback</a>
</h3>

<p align="center">
<a href="LICENSE"><img alt="License: GPLv3 or later" src="https://img.shields.io/badge/license-GPL%20V3%2B-green?style=plastic"></a>
<a href="https://github.com/manticoresoftware/manticoresearch/actions/workflows/test.yml?query=branch%3Amain"><img alt="GitHub Actions Workflow Status" src="https://img.shields.io/github/actions/workflow/status/manticoresoftware/manticoresearch/test.yml?branch=main&style=plastic&color=green"></a>
<a href="https://twitter.com/manticoresearch"><img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/manticoresearch?color=green&logo=Twitter&style=plastic"></a>
<a href="http://slack.manticoresearch.com/"><img alt="Slack" src="https://img.shields.io/badge/slack-manticoresearch-green.svg?logo=slack&style=plastic"></a>
<a href="https://github.com/manticoresoftware/docker"><img alt="Docker pulls" src="https://img.shields.io/docker/pulls/manticoresearch/manticore?color=green&style=plastic"></a>
<a href="https://eepurl.com/dkUTHv"><img alt="Newsletter" src="https://img.shields.io/badge/newsletter-green?style=plastic"></a>
<a href="https://github.com/manticoresoftware/manticoresearch/graphs/commit-activity"><img alt="Activity" src="https://img.shields.io/github/commit-activity/m/manticoresoftware/manticoresearch?color=green&style=plastic"></a>
<a href="https://github.com/manticoresoftware/manticoresearch/issues?q=is%3Aissue+is%3Aclosed"><img alt="GitHub closed issues" src="https://img.shields.io/github/issues-closed/manticoresoftware/manticoresearch?color=green&style=plastic"></a>
</p>

*Section quoted from the upstream readme.*
---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | C/C++ / CMake |
| Manifests detected | CMakeLists.txt, configure |
| Files in snapshot | 2546 |
| Lines of code | 344971 |
| Dependency references | 13 |
| Dependencies by ecosystem | cargo: 5, go: 2, native: 5, npm: 1 |
| Upstream license | GPL-3.0 |
| Overlay license | Anticommons 0.1.0 |

Top dependency references recorded in the benchmark snapshot:

| Ecosystem | Name | Version | Source file |
|-----------|------|---------|-------------|
| native | Threads | - | CMakeLists.txt |
| native | PythonInterp | - | test/CMakeLists.txt |
| cargo | name | sqlx_prepared_stmt | test/sqlx_prepared_stmt/Cargo.toml |
| cargo | version | 0.1.0 | test/sqlx_prepared_stmt/Cargo.toml |
| cargo | edition | 2021 | test/sqlx_prepared_stmt/Cargo.toml |
| cargo | sqlx | 0.7 | test/sqlx_prepared_stmt/Cargo.toml |
| cargo | tokio | 1 | test/sqlx_prepared_stmt/Cargo.toml |
| npm | mysql2 | ^3.11.0 | test/node_prepared_stmt/package.json |
| go | github.com/go-sql-driver/mysql | v1.8.1 | test/go_prepared_stmt/go.mod |
| go | filippo.io/edwards25519 | v1.1.0 | test/go_prepared_stmt/go.mod |
| native | Boost | - | src/CMakeLists.txt |
| native | PythonInterp | - | src/CMakeLists.txt |
| native | Threads | - | libre2/CMakeLists.txt |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

- Cost-based optimizer determines the most efficient execution plan of a search query
* Data types:
  - full-text field - inverted index
  - [UUID document IDs](https://manual.manticoresearch.com/Creating_a_table/Data_types#UUID-document-IDs) for real-time tables
  - int, bigint and float numeric fields in row-wise and columnar fashion
  - multi-value attributes (array)
  - string and JSON
  - on-disk "[stored](https://play.manticoresearch.com/docstore/)" for key-value purpose
* Integrations:
  - [Sync from MySQL and PostgreSQL](https://manual.manticoresearch.com/Creating_a_table/Local_tables/Plain_table#Plain-table)
  - [Sync from XML](https://manual.manticoresearch.com/Adding_data_from_external_storages/Fetching_from_XML_streams#XML-file-format)
  - [Sync from CSV](https://manual.manticoresearch.com/Adding_data_from_external_storages/Fetching_from_CSV,TSV#Fetching-from-TSV,CSV)
  - [Sync from ODBC](https://manual.manticoresearch.com/Data_creation_and_modification/Adding_data_from_external_storages/Fetching_from_databases/Introduction#Introduction)
  - [Sync from MS SQL](https://manual.manticoresearch.com/Data_creation_and_modification/Adding_data_from_external_storages/Fetching_from_databases/Introduction#Introduction)
  - [Sync from Kafka](https://manual.manticoresearch.com/Integration/Kafka)
  - [With MySQL as a storage engine](https://manual.manticoresearch.com/Extensions/SphinxSE#Using-SphinxSE)
  - [With MySQL via FEDERATED engine](https://manual.manticoresearch.com/Extensions/FEDERATED)
  - [ProxySQL](https://manticoresearch.com/blog/using-proxysql-to-route-inserts-in-a-distributed-realtime-index/)
  - [Apache Superset](https://manticoresearch.com/blog/manticoresearch-apache-superset-integration/)
  - [Grafana](https://manticoresearch.com/blog/manticoresearch-grafana-integration/)
  - [Fluentbit](https://manticoresearch.com/blog/integration-of-manticore-with-fluentbit/)
  - [Kibana](https://manual.manticoresearch.com/Integration/Kibana#Integration-of-Manticore-with-Kibana) ([Demo](https://github.com/manticoresoftware/kibana-demo))
  - [Logstash/Filebeat](https://manticoresearch.com/blog/integration-of-manticore-with-logstash-filebeat/)
  - [Vector.dev](https://manticoresearch.com/blog/integration-of-manticore-with-vectordev/)
  - [Mysqldump](https://manual.manticoresearch.com/Securing_and_compacting_a_table/Backup_and_restore#Backup-and-restore-with-mysqldump)
  - [Manticore Columnar Library](https://github.com/manticoresoftware/columnar)

*Section quoted from the upstream readme.*
Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

*Excerpt from upstream `CONTRIBUTING.md`:*

# Contributing to Manticore Search

We're happy you want to contribute!
This project adheres to the Manticore Search [Code of Conduct](https://github.com/manticoresoftware/manticore/blob/main/CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. 
There are many ways to cotribute, from helping others, spread the word, submitting bug reports and feature requests or writing code.

## Reporting bugs

No software is perfect, so bugs can happen. 
Before submitting a bug make sure to :

* check if the bug is not already reported at  [issues list](https://github.com/manticoresoftware/manticore/issues) 
* the bug reproduces on the latest version. If you are using an older version, it is possible that your bug may be fixed already. 
 

In case the bug is already reported, you can help by participate in the discussion by confirming you are affected as well and check if you can provide additional information about the bug.

To make things easier and fix it faster, try to provide a small test case which can be run to confirm your bug. The maintainers needs to be able to reproduce the bug in order to fix it.

If you can provide sample data, but it's big, we have a [Write-only FTP](https://github.com/manticoresoftware/manticore/wiki/Write-only-FTP) for uploading larger data on one of our servers.

Follow the [issue template](https://github.com/manticoresoftware/manticore/blob/main/ISSUE_TEMPLATE.md) guideline about the information the bug report should include.

## Feature requests

A lot of features in Manticore Search come from user's requests. To make a feature request, either open an issue on our [issues list](https://github.com/manticoresoftware/manticore/issues) on Github or on [Feature Requests](https://forum.manticoresearch.com/c/feature-requests) forum section. Describe in detail the feature you would like to see, which are it's use cases and how it should work.

## Code changes

We recommend opening first a github issue describing your proposed changed and check if they fit with what maintainers are doing and have planned. 

### Fork/source the project
source/fork the main branch via Github or 'git source'.
Don't work directly on the main branch, but create a branch.

### Testing and submiting changes

Manticore Search code comes with a test suite which must be run to ensure your changes don't create any regression. Read the [TESTING](https://github.com/manticoresoftware/manticore/blob/main/TESTING.md) guide for how to run the tests.

W

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: GPL-3.0** (evidence: `LICENSE` in the upstream snapshot).

License file excerpt:

```text
                    GNU GENERAL PUBLIC LICENSE
                       Version 3, 29 June 2007

 Copyright (C) 2007 Free Software Foundation, Inc. <https://fsf.org/>
 Everyone is permitted to copy and distribute verbatim copies
 of this license document, but changing it is not allowed.

                            Preamble

  The GNU General Public License is a free, copyleft license for
software and other kinds of works.

  The licenses for most software and other practical works are designed
to take away your freedom to share and change the works.  By contrast,
the GNU General Public License is intended to guarantee your freedom to
share and change all versions of a program--to make sure it remains free
software for all its users.  We, the Free Software Foundation, use the
GNU General Public License for most of our software; it applies also to
any other work released this way by its authors.  You can apply it to
your programs, too.
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original GPL-3.0 terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `GPL-3.0` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `MANTICORESEARCH` (category: SEARCH ENGINES)
- **Upstream URL:** https://github.com/manticoresoftware/manticoresearch-php
- **Pinned commit (SHA):** `448a133e561ba90fa027c838bbec6353c6780847`
- **Branch:** master
- **Pin provenance:** GitHub API commits/master. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`e2c819c80000a08b67805a729c6c9ac481d1c90f0cb18042273cf07a187272cb`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| DANS (KNAW/NWO, Netherlands) | 10.17026/PT | EU-recognised archive |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe
and Mail, Business Insider, National Post, Financial Post, StreetInsider,
Digital Journal, Barchart, International Business Times, and Fox News.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

