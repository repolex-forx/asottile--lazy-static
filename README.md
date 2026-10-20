# Repolex Knowledge Graph of asottile/lazy-static

RDF knowledge graph data for [asottile/lazy-static](https://github.com/asottile/lazy-static), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/lazy-static
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 64447c593254b3abeb0a2f03113368b52a69c084
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 64447c593254b3abeb0a2f03113368b52a69c084
│           └── chunk-001.nq.gz
├── blob
│   ├── 218ad6d7953a37101145568d90d337953cd9ec32.nq.gz
│   ├── 2ffaa1693add0406afeeb0cf81572e5c8223edb1.nq.gz
│   ├── 311a5261c19caac2674f95c763cb936a61270ced.nq.gz
│   ├── 713633cc2bf99b0e752b68006bb0220b42f40067.nq.gz
│   ├── 7f4d45a64dc994d0cf99a5d6737b32445ab7a8cd.nq.gz
│   ├── 8bf1ba938af9b4993f625db4fc6e708be9f3f3b7.nq.gz
│   ├── 8c38c3fa07daab3596dae959bfec1e3571868cb0.nq.gz
│   ├── 98f8dbeef2687a4b6028ba3a7886bb6763e86d4d.nq.gz
│   ├── 9b3a66ba16fc2c7c0f1cee7131c98c8adcc3daa3.nq.gz
│   ├── a0738a9028039732b05139690c94855a2184a2e1.nq.gz
│   ├── c47cb99119636b628e5f3c4d9fbbe009678d8f92.nq.gz
│   ├── ca1d90ea180858ae143c0e62d920e350d3acc62d.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 64447c593254b3abeb0a2f03113368b52a69c084.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 20 files
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

[asottile/lazy-static](https://github.com/asottile/lazy-static)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
