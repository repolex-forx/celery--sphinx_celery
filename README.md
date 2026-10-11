# Repolex Knowledge Graph of celery/sphinx_celery

RDF knowledge graph data for [celery/sphinx_celery](https://github.com/celery/sphinx_celery), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download celery/sphinx_celery
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 715a76ddbb8da0e953496419c3c38ea513cc774f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 715a76ddbb8da0e953496419c3c38ea513cc774f
│           └── chunk-001.nq.gz
├── blob
│   ├── 04381c194bc8a6afd68293b1f1fe26fc36be7597.nq.gz
│   ├── 0b1c672a8d6cda0c8decb678f83076178bad5bf9.nq.gz
│   ├── 0b212987df661cc3f3c3b1d8094c23beadb1e841.nq.gz
│   ├── 22fb1f902a9f8dced0c3180ed0187471396cbf8b.nq.gz
│   ├── 277d0462398afa18be7fc30c4bd32823131f7b9f.nq.gz
│   ├── 36cafd9d98429d4e70f2531164c389875533aa82.nq.gz
│   ├── 3a472bc836c30415445def35bc58338a1cbe38c5.nq.gz
│   ├── 3f05628255a9939606ed7426e91be18d07581d23.nq.gz
│   ├── 3fced97e7c7494565d0baf5f92b9701e3db73f67.nq.gz
│   ├── 42ac5fdf61bf51a2c5c688b661e5d56ab283da24.nq.gz
│   ├── 65810862d6ff3be1356c7834770d34df11bcc0a5.nq.gz
│   ├── 79e61fe34e5f2c6a3f0a4cf570078a2b414286f4.nq.gz
│   ├── 7e42a5f57150c5ecd429cb3d7220852762bccf58.nq.gz
│   ├── 807081aa956ec3a9c2b2782b76e254941f02b22f.nq.gz
│   ├── 80bc9cc405f240efb8127020ed7ad77facb742c7.nq.gz
│   ├── 862ae879af935b1c10e485554e98db2699ddcf18.nq.gz
│   ├── 8dc7b79a846d96302ee19cbd34fe657bcabc34cc.nq.gz
│   ├── 951640c94f7846f1b34166fb0591eff6463dd9d0.nq.gz
│   ├── 9a01e7a6cbab9450f0d58d09bc55c986884782b1.nq.gz
│   ├── 9aaf3658ccc0be20bd551043fb171aa015ac2e7d.nq.gz
│   ├── 9ad052cc5b28950b4fbe02d41b0270604118b3b2.nq.gz
│   ├── a81dcc4581f2b228522a3c0f233a63e6209d5141.nq.gz
│   ├── b384ee215f7d255f01131352f352a71e70ad5471.nq.gz
│   ├── b4f9eb4b53eae54ed53d83fa5195e323dbfac4ec.nq.gz
│   ├── b530f637f73af7d839b0642798cff525a9e59085.nq.gz
│   ├── b68da70491c20681eefdc69daf88f25e499dd759.nq.gz
│   ├── bfcf66ac10a9104174ebf83acc8b0594eff2675a.nq.gz
│   ├── c2f72eef4db23b8364408329ca4f7419b651ddba.nq.gz
│   ├── d78cca33ae29367cec203a13de150c6a37c9971f.nq.gz
│   ├── e51226a930e0b2cb928d576d2642a140489f1b00.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ebd5522c9d3d264db50d53202e705b7f338a26e0.nq.gz
│   ├── f094fca470315354410729263dc8c49efff84814.nq.gz
│   └── ff96ee576437fc8164fd5ac68c36afe6f4125592.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 715a76ddbb8da0e953496419c3c38ea513cc774f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 42 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[celery/sphinx_celery](https://github.com/celery/sphinx_celery)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
