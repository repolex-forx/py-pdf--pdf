# Repolex Knowledge Graph of py-pdf/pdf

RDF knowledge graph data for [py-pdf/pdf](https://github.com/py-pdf/pdf), parsed by [repolex](https://repolex.ai).

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
rlex download py-pdf/pdf
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 899bff5cbd119db2e336e76b881d6a8b7d45ba68
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 899bff5cbd119db2e336e76b881d6a8b7d45ba68
│           └── chunk-001.nq.gz
├── blob
│   ├── 401b6d54f34525aabbfb0f53e350e119d67a66fb.nq.gz
│   ├── 4bea1794e7b637f155dcff0df9895d48bcfe9202.nq.gz
│   ├── 5ce6cb05259d9ccc91630d949f75a69492a15237.nq.gz
│   ├── 658cf9c0ad8e735a2fc228b7d2548c09f6679627.nq.gz
│   ├── 7795d0bf61d01205612133e56ded0748a01fb0f0.nq.gz
│   ├── 8d1d144e3202ea52b01bfaf2dd3b5535baaf73b7.nq.gz
│   ├── 9264739c581df234c37941c122b50f2bf3c9e13d.nq.gz
│   ├── afb42411d30470cc83e63d64b480c657efce9b05.nq.gz
│   ├── b4a5d6c545da6edbeab63fcb8ed6a6aeafce5838.nq.gz
│   ├── b6e47617de110dea7ca47e087ff1347cc2646eda.nq.gz
│   ├── ccfc53b089ae2692a7b844afad1d0c7dede1cf7c.nq.gz
│   ├── cf6143c0053b5e84faaaca27cf980461a4d4e927.nq.gz
│   ├── d58f17623612cf39ed52a4542f5ceacfa32ca887.nq.gz
│   ├── de3e0c1609eea268c2d5967d713cae893b51b4eb.nq.gz
│   ├── df364248f42967e404dd7dbc8d065e36bfa8d8ef.nq.gz
│   ├── e193b3fb25e059bf876071ee7d00a6dd533ecf6d.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e9d3a9b8aba0325bb57379fdb51e1d9a33fd0018.nq.gz
│   ├── ecf9d653735bace2cc9b93030f535019714a2a18.nq.gz
│   └── ef5c40a15a54480afebac8a81e374b80fe235a93.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 899bff5cbd119db2e336e76b881d6a8b7d45ba68.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 27 files
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

[py-pdf/pdf](https://github.com/py-pdf/pdf)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
