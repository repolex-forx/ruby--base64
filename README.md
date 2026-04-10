# Repolex Knowledge Graph of ruby/base64

RDF knowledge graph data for [ruby/base64](https://github.com/ruby/base64), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download ruby/base64
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 09e839e5ad7642276fb27aa1a159f9c78690ea4e
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 09e839e5ad7642276fb27aa1a159f9c78690ea4e.nq.gz
│   └── repolex
│       └── 09e839e5ad7642276fb27aa1a159f9c78690ea4e
│           └── chunk-001.nq.gz
├── blob
│   ├── 06d6f4c047fbc6c4a85e198cb6d5e119ebc127ea.nq.gz
│   ├── 30baabd94e04ff53834fa3334b5811e2c53b2770.nq.gz
│   ├── 4ea57987f435966482f3bc93e09ab1dd3c9cff58.nq.gz
│   ├── 64a2b4b7a7bbeebf22ef72ea0e75c34893ec5273.nq.gz
│   ├── a009caefea81f259e19d842356cb43ecf1710fff.nq.gz
│   ├── a29c58e736e8bd0a5e1ecc3f9dd092fb3e5a091e.nq.gz
│   ├── b18fd2935736768f4b1eb12f15709ba4c2f05171.nq.gz
│   ├── c013b7c1c25dad3db4b1bf10b5f420f7f9f51891.nq.gz
│   ├── cd2ecc18ea0ae7879d022d48ef638220a84ba595.nq.gz
│   ├── ce716043a8eadb054ba5cee9470836aecf254748.nq.gz
│   ├── dce67d860af47a4eb630117ce03624bae45dcf26.nq.gz
│   └── eb8619204cce16b3e74cd5b57de7983a7624c297.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 09e839e5ad7642276fb27aa1a159f9c78690ea4e.nq.gz
├── filetree
│   └── 09e839e5ad7642276fb27aa1a159f9c78690ea4e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 22 files
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

## Source repository

[ruby/base64](https://github.com/ruby/base64)

---
*Parsed on 2026-04-10 by [repolex](https://repolex.ai)*
