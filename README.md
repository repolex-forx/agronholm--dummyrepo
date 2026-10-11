# Repolex Knowledge Graph of agronholm/dummyrepo

RDF knowledge graph data for [agronholm/dummyrepo](https://github.com/agronholm/dummyrepo), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/dummyrepo
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 69ea67ec88e556eb36b158506d1222a68e58f28c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 69ea67ec88e556eb36b158506d1222a68e58f28c
│           └── chunk-001.nq.gz
├── blob
│   ├── 0495c4a88caed0f036ffab0948c17d4b5fdc96c1.nq.gz
│   └── bb761dedd273709651613f13134e23bdef5e6d5c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 69ea67ec88e556eb36b158506d1222a68e58f28c.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 8 files
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

[agronholm/dummyrepo](https://github.com/agronholm/dummyrepo)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
