# Repolex Knowledge Graph of optuna/kurobako-py

RDF knowledge graph data for [optuna/kurobako-py](https://github.com/optuna/kurobako-py), parsed by [repolex](https://repolex.ai).

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
rlex download optuna/kurobako-py
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bd1d6448dd5388ff4fcb3146dad3869aec77d0d7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── bd1d6448dd5388ff4fcb3146dad3869aec77d0d7
│           └── chunk-001.nq.gz
├── blob
│   ├── 1aba38f67a2211cf5b09466d7b411206cb7223bf.nq.gz
│   ├── 1f0b734eb1e6c2b158b511497a513e7d626743fb.nq.gz
│   ├── 2025285cf81f9d8a23ac9dc4d1a801875f37a295.nq.gz
│   ├── 583304c443919950a5fe7b4e907e7a2831abd2da.nq.gz
│   ├── 58844f566eccc84c36f508bd34c14e764f74a965.nq.gz
│   ├── 60f05c23496186656f63e4a5e6860191f7f89ce8.nq.gz
│   ├── 60ffdd5553189fb98af55cf4aa55eedda2ffedc6.nq.gz
│   ├── 9aadf9357ecf41ff4818037023c315bea1491b70.nq.gz
│   ├── a020597327ff0de35ae5e787e2c93b364d64bde3.nq.gz
│   ├── abd62d7d54e007460c7d46a2387a1c50d923173b.nq.gz
│   ├── acb77de0bdc37063d88868170590788123be5edf.nq.gz
│   ├── e443b2ceeb0d872211af3d55bab3c3b2125ab0a2.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bd1d6448dd5388ff4fcb3146dad3869aec77d0d7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[optuna/kurobako-py](https://github.com/optuna/kurobako-py)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
