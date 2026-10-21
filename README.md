# Repolex Knowledge Graph of sanic-org/html5tagger

RDF knowledge graph data for [sanic-org/html5tagger](https://github.com/sanic-org/html5tagger), parsed by [repolex](https://repolex.ai).

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
rlex download sanic-org/html5tagger
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e3e0c044784d7409fcc823dde1bd83d531b4c288
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e3e0c044784d7409fcc823dde1bd83d531b4c288
│           └── chunk-001.nq.gz
├── blob
│   ├── 02d0eb1b364fac99737dae593245efcc59f7d530.nq.gz
│   ├── 1514a727e8afdfd25eba5b83df56203dd40a72cc.nq.gz
│   ├── 2437fc3b99235205e29237eae82303b798a10bd6.nq.gz
│   ├── 2b44522778ea0029126f253331edd6a07d6c55e9.nq.gz
│   ├── 2d3d236910770dd01cb91a4c9dcd42fbbf639e2d.nq.gz
│   ├── 31e4352f520fca2416d819ad501db6448737e3a7.nq.gz
│   ├── 43e508cbf7290aac80688ac3f9d690ac17caceaf.nq.gz
│   ├── 4c1edd3e886ef870c70e5032bc829b3d65fd9abb.nq.gz
│   ├── 632f738cd01c0f00fb9e0d0fa805ada336b89434.nq.gz
│   ├── 65ca7f3b14ebb5ffbe3fe99939e462935d2173e8.nq.gz
│   ├── 88cc2b1ad4c6ae9418fc24b04e3661c3e95a4fd7.nq.gz
│   ├── 97d053391c3f6a7d621ce6d3bb9c8189f026566e.nq.gz
│   ├── abfb50ef129a7bd4f87df0b3ab22168790ce2a9e.nq.gz
│   ├── b27cd3c9386c8cc9c373d97e1b2e06d1560423cb.nq.gz
│   ├── b3dbff00cd9979ce8009daa72f87fabe1d8f3484.nq.gz
│   ├── b3e4a057d409e10ee27504a31e540e393caef352.nq.gz
│   ├── b3faa41a78bcd51e921a8d4dd34e0428a1b0ef7f.nq.gz
│   ├── c1809b578a058a9713130aa372d5956f5e51664c.nq.gz
│   ├── de0d3b7e4e07dee788daf9ac0cd4690171bffb95.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e937d4e3f7ed1377d0459cf8b3afdb3404a28635.nq.gz
│   └── f195f2ff406627572a5216b2468e6367bf3e2524.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e3e0c044784d7409fcc823dde1bd83d531b4c288.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 30 files
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

[sanic-org/html5tagger](https://github.com/sanic-org/html5tagger)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
