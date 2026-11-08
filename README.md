# Repolex Knowledge Graph of PrefectHQ/is-your-mcp-server-good

RDF knowledge graph data for [PrefectHQ/is-your-mcp-server-good](https://github.com/PrefectHQ/is-your-mcp-server-good), parsed by [repolex](https://repolex.ai).

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
rlex download PrefectHQ/is-your-mcp-server-good
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a08e8bd8097fb633cf40b41a272ef15c7a35e02e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a08e8bd8097fb633cf40b41a272ef15c7a35e02e
│           └── chunk-001.nq.gz
├── blob
│   ├── 1b8367795317750c7fd0f285db66a045d5584b38.nq.gz
│   ├── 6ca89fdd67699e0f0762df2584b44258a05f2639.nq.gz
│   ├── 81026485e4070a1d9dba3d2d52ffb9cb4feb3adc.nq.gz
│   ├── a230a78aea291ec7c0c35eefbc89b3898612a118.nq.gz
│   ├── d79d53dd32633583592343fe37e1c7ad409bd685.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e960de8248eaab51bf7753bcf98957133112c24f.nq.gz
│   ├── f49a4e16e68b128803cc2dcea614603632b04eac.nq.gz
│   └── f76f3e1ccd04457bbf11cb7245bce9bd470a95ca.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a08e8bd8097fb633cf40b41a272ef15c7a35e02e.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 16 files
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

[PrefectHQ/is-your-mcp-server-good](https://github.com/PrefectHQ/is-your-mcp-server-good)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
