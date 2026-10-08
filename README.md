# Repolex Knowledge Graph of block/bitcoin-augur-benchmarking

RDF knowledge graph data for [block/bitcoin-augur-benchmarking](https://github.com/block/bitcoin-augur-benchmarking), parsed by [repolex](https://repolex.ai).

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
rlex download block/bitcoin-augur-benchmarking
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 55b4818186834f62983a191f8e734200c74a53ee
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 55b4818186834f62983a191f8e734200c74a53ee.nq.gz
│   └── repolex
│       └── 55b4818186834f62983a191f8e734200c74a53ee
│           └── chunk-001.nq.gz
├── blob
│   ├── 01f0cb07bb642a355b41689877e23f307d563be6.nq.gz
│   ├── 1461af1fa54f85085860c3a7e650bcb40804178a.nq.gz
│   ├── 1bc469e68eb776aa52185c6cbfc5cdcaee837ce3.nq.gz
│   ├── 46228b0624e4643b1415c427b844e42b1b43d7a3.nq.gz
│   ├── 59ca81bf8f29ce65c5ef362518239275264f311d.nq.gz
│   ├── 60baa9cb833f9e075739f327f4fe68477c84a093.nq.gz
│   ├── 6bccf43368fd7c96d9c659562a5142b8b8cb98a1.nq.gz
│   └── d36cefbf88ac9837148efdfe24c5e020e5b26b7b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 55b4818186834f62983a191f8e734200c74a53ee.nq.gz
├── filetree
│   └── 55b4818186834f62983a191f8e734200c74a53ee.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 17 files
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

[block/bitcoin-augur-benchmarking](https://github.com/block/bitcoin-augur-benchmarking)

---
*Parsed on 2026-10-08 by [repolex](https://repolex.ai)*
