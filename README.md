# Repolex Knowledge Graph of Kozea/pygal_maps_fr

RDF knowledge graph data for [Kozea/pygal_maps_fr](https://github.com/Kozea/pygal_maps_fr), parsed by [repolex](https://repolex.ai).

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
rlex download Kozea/pygal_maps_fr
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 273f6cea52df8d16a5e101ad2491c1663a6e098d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 273f6cea52df8d16a5e101ad2491c1663a6e098d
│           └── chunk-001.nq.gz
├── blob
│   ├── 046c62d7e694f24f859edb0b1af960b72bf1da95.nq.gz
│   ├── 0d02fbdc9c01329e788484edbe4c6dccc95dbd03.nq.gz
│   ├── 1a89e15e03b8f4044112b6441c28984ae2d5eff4.nq.gz
│   ├── 76479d7b1c5361e1d591f2b9bb930bc4a9446bf5.nq.gz
│   ├── a6756505bfb6a42a91442863362340a53b52809b.nq.gz
│   ├── b75b9f7f5591f96e2be0d3b82dcc331515ce6765.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 273f6cea52df8d16a5e101ad2491c1663a6e098d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
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

[Kozea/pygal_maps_fr](https://github.com/Kozea/pygal_maps_fr)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
