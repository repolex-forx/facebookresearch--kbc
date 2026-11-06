# Repolex Knowledge Graph of facebookresearch/kbc

RDF knowledge graph data for [facebookresearch/kbc](https://github.com/facebookresearch/kbc), parsed by [repolex](https://repolex.ai).

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
rlex download facebookresearch/kbc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 248e93136448661cac54020054b929997394f3d2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 248e93136448661cac54020054b929997394f3d2
│           └── chunk-001.nq.gz
├── blob
│   ├── 2355b82a6ed4cf195f546d730649f84cd56fe071.nq.gz
│   ├── 571f5c700cd6c851f907c5600b7bc2e6ebbd4917.nq.gz
│   ├── 6c094fa9155dd65649558213275c86eee057bd54.nq.gz
│   ├── 748ee558bb13f7d4ef4b1da1d3eba0240c70be45.nq.gz
│   ├── 7d8631ac36bf522cf8296a2ca13721e927643975.nq.gz
│   ├── 98ab2019a7214e57dfbfd9ee7bb5a765313817de.nq.gz
│   ├── 9985a4a3530a460afa3b81ac91b7fa5a8bea2b5f.nq.gz
│   ├── a93676f08873fdd0bbb35946d27905407c0538b4.nq.gz
│   ├── b7a0eb87d312c2edc42898856d2cc2343a541ec9.nq.gz
│   ├── b97bc7b5537abba5b90f45a854ed7241ac2d0d11.nq.gz
│   ├── c1ad05a1f81aae555ab8c9d119951e8f39fd27b4.nq.gz
│   ├── c4d32c287deb292c502c1ef649f0d9c15c07def9.nq.gz
│   ├── c617f3688d3428940c6dfa7fbfcfa11d1e3ee7e7.nq.gz
│   ├── dabe37b4417d9863f1fb7244f156eed4f1253df7.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 248e93136448661cac54020054b929997394f3d2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[facebookresearch/kbc](https://github.com/facebookresearch/kbc)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
