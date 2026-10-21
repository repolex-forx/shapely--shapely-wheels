# Repolex Knowledge Graph of shapely/shapely-wheels

RDF knowledge graph data for [shapely/shapely-wheels](https://github.com/shapely/shapely-wheels), parsed by [repolex](https://repolex.ai).

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
rlex download shapely/shapely-wheels
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 33ad6aa77f146359307857cd48770ddb89a51e4e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 33ad6aa77f146359307857cd48770ddb89a51e4e
│           └── chunk-001.nq.gz
├── blob
│   ├── 009792c90f3a95825e5294c5a2e011f5b859041f.nq.gz
│   ├── 0194389e2f419c7ab72dac455de506cd469e2193.nq.gz
│   ├── 4dbaf2723cbd52188f32eb633ce061db8436c70d.nq.gz
│   ├── 609d141dee4ac5b399d0c4cda1ab2998a30b6699.nq.gz
│   ├── 6a3c91b75480d1b4eb8202c5cc8c1c992e46d69b.nq.gz
│   ├── 70065d7d6ce19352026a97749424685d3d451c60.nq.gz
│   ├── bbb46635e1869b204cd6648836948eee7ecdb9d7.nq.gz
│   ├── cb352a5edc77f4b71633c27e4a2920f3100ddfa5.nq.gz
│   ├── df896639555fb66bd5011877f594644ccdc0bca2.nq.gz
│   ├── e076b254cddd92c42d1819e669c05dbd0f410151.nq.gz
│   └── f564c2fe74f5abb33bba79ef82e5427058d5964d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 33ad6aa77f146359307857cd48770ddb89a51e4e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[shapely/shapely-wheels](https://github.com/shapely/shapely-wheels)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
