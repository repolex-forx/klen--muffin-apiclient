# Repolex Knowledge Graph of klen/muffin-apiclient

RDF knowledge graph data for [klen/muffin-apiclient](https://github.com/klen/muffin-apiclient), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-apiclient
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 37fe19602fd086c259c983f658229b5b6eea89b4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 37fe19602fd086c259c983f658229b5b6eea89b4
│           └── chunk-001.nq.gz
├── blob
│   ├── 00670cf73d9c1862810bff9716cb6b86b074fba3.nq.gz
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 1f2ac234b7e8b9d3b33a72ac524d84c7bde4a60a.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 3a37db158765ee29e6b46b74d442262fc77f61d6.nq.gz
│   ├── 3d3de9177b065ccd2b82e03a2cd70dd8b0e5323a.nq.gz
│   ├── 4a060cc8ce501e4a5b9157c2f5ed52285582dd60.nq.gz
│   ├── 4bc56ecf78ad5a1a4f69c03367448567c8fe654e.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 5f89bcab9730d6331b2a227c05c62fa0c9344c55.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 80826d975aa6e305dddbe44be4b9e7ea0ca1dd87.nq.gz
│   ├── 865fecd99cd8546c92e63ec5b74787c7a966bf39.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── d5967885cf2b07465203d3e529ba018dde5304c5.nq.gz
│   ├── de4b3e405f795bbf0a13d27a2141cf0d12d3d312.nq.gz
│   ├── dee1de9d3a196b6db29970cee6e253f1f63dd53f.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
│   ├── fe397bfecbfd1467b701ca9395b9527dde71d78a.nq.gz
│   └── ff00e5d0b915b4820cb44c23a2a9893073a67ecf.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 37fe19602fd086c259c983f658229b5b6eea89b4.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 30 files
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

[klen/muffin-apiclient](https://github.com/klen/muffin-apiclient)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
