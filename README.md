# Repolex Knowledge Graph of sphinx-gallery/sample-project

RDF knowledge graph data for [sphinx-gallery/sample-project](https://github.com/sphinx-gallery/sample-project), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-gallery/sample-project
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b97877999179269aabe5ef705b85a627c4581c1c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b97877999179269aabe5ef705b85a627c4581c1c
│           └── chunk-001.nq.gz
├── blob
│   ├── 0490d9a30c7c817ef3933eaaeda7b775ce567237.nq.gz
│   ├── 127314be577bf435f012ab04e0821c8cf14d802d.nq.gz
│   ├── 16d3d3ad4d0219bac5755ecc34172351fee41f74.nq.gz
│   ├── 1b1d7c4f895ae016b6182ada897ac879e43b32fb.nq.gz
│   ├── 1bb9e960b331b843dec4cdb921b5b737780fe039.nq.gz
│   ├── 2119f51099bf37e4fdb6071dce9f451ea44c62dd.nq.gz
│   ├── 24a251bd099b83f76471e245af3f7de38ce7c92e.nq.gz
│   ├── 3fe18e594ef2eb864ffc8d6c643888cbc93e40fe.nq.gz
│   ├── 49c3fd0b4e6da13caca1c64cdecbc9803b8e70ac.nq.gz
│   ├── 4db85196e54e617f31c0b58d008a38994b1850e5.nq.gz
│   ├── 5769f54fe6a85b3f5b3127b963bfe1cb1c45abce.nq.gz
│   ├── 7ac93c2b45aa97a732fd3734cdf7dc2bccf2a8c3.nq.gz
│   ├── 7c16a68d80dcf9245d847f118afc55486ddd48a6.nq.gz
│   ├── 8393bc832003b27414d3babaa25df3b4d1e9d9dc.nq.gz
│   ├── 93d12609c797ef866758ac3f5446f364312ef540.nq.gz
│   ├── a7c46d031aca49ee8ad9912b5edbbac66980af4a.nq.gz
│   ├── ae8741235dd88fcf5f9bc668c3684ca1480ea404.nq.gz
│   ├── d0fb7c44a245ba9b2194ca3c131d96b3adfe359f.nq.gz
│   ├── d49c43a5f926aede2ca46dc0035b41c4ea94467e.nq.gz
│   ├── d4bb2cbb9eddb1bb1b4f366623044af8e4830919.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f77958ec340efe5bd5026452b3df8450692bec04.nq.gz
│   └── fae1a63567ad986e10037068c90001a005c7cbcc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b97877999179269aabe5ef705b85a627c4581c1c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[sphinx-gallery/sample-project](https://github.com/sphinx-gallery/sample-project)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
