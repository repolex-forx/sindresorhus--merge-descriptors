# Repolex Knowledge Graph of sindresorhus/merge-descriptors

RDF knowledge graph data for [sindresorhus/merge-descriptors](https://github.com/sindresorhus/merge-descriptors), parsed by [repolex](https://repolex.ai).

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
lexq download sindresorhus/merge-descriptors
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b497f611ec85031e00c2f3cdbb327a550028a7bf
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── b497f611ec85031e00c2f3cdbb327a550028a7bf.nq.gz
│   └── repolex
│       └── b497f611ec85031e00c2f3cdbb327a550028a7bf
│           └── chunk-001.nq.gz
├── blob
│   ├── 1c6314a31833395fd5ff016a6506bdd51860657c.nq.gz
│   ├── 1dee67d843668d895d55ed100debc2a1b36254e6.nq.gz
│   ├── 239ecff1372358a22aa99dcbb375fdad7abba817.nq.gz
│   ├── 2dca3062786160089d5cb829e37c971208011d3f.nq.gz
│   ├── 346585cf904a9126a589404f48706564d3791659.nq.gz
│   ├── 43c97e719a5a824700932f72e6e7e6748ce45d01.nq.gz
│   ├── 51228e5cecc2929c27b40f855a6f4eb4fb9baf7b.nq.gz
│   ├── 6313b56c57848efce05faa7aa7e901ccfc2886ea.nq.gz
│   ├── 9bedb250ba6f5976c708674d9d6b539e7ff3050e.nq.gz
│   ├── c509d4557c0d11a3f7ea08d5e4ff0c77ff91f4cf.nq.gz
│   └── df8f91f445b1ef0be11552801e36bf5eedea8910.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── b497f611ec85031e00c2f3cdbb327a550028a7bf.nq.gz
├── filetree
│   └── b497f611ec85031e00c2f3cdbb327a550028a7bf.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 21 files
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

[sindresorhus/merge-descriptors](https://github.com/sindresorhus/merge-descriptors)

---
*Parsed on 2026-04-10 by [repolex](https://repolex.ai)*
