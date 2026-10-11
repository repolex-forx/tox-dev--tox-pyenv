# Repolex Knowledge Graph of tox-dev/tox-pyenv

RDF knowledge graph data for [tox-dev/tox-pyenv](https://github.com/tox-dev/tox-pyenv), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/tox-pyenv
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 464180efa7eed7666d4a240fd3fa7390e3450397
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 464180efa7eed7666d4a240fd3fa7390e3450397
│           └── chunk-001.nq.gz
├── blob
│   ├── 20c244ce84d6b2804cb43dc11fd0b315f04e0a45.nq.gz
│   ├── 31b40f29a2c5af2e20ed9e92cc1f1b7628e4f1ad.nq.gz
│   ├── 5e4090017a9bec5de60a745d17007a9e95f31a43.nq.gz
│   ├── 738d9f5a31d1e230403bd5c4802d7bcb721b5297.nq.gz
│   ├── 775fa7c4a1d9855357e11b3f8ae7ebfffb473bbd.nq.gz
│   ├── 825a3ed3eaa3a9e7fdab43c6f015c178f54f2005.nq.gz
│   ├── 8f71f43fee3f78649d238238cbde51e6d7055c82.nq.gz
│   ├── 9ee7f45de59e8e6cac935581b05c611d403e9f88.nq.gz
│   ├── b50cd225bc9f280b651c2a2f0fac031c8b5a65bb.nq.gz
│   ├── ba74660506d90c514ee1d32bf4eb5ecb0af14075.nq.gz
│   ├── e3144ca79b7bd4acd99d65043f4d9348d71eee2e.nq.gz
│   └── e61f07483b4afe382ecdda8e8bdf86538a852357.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 464180efa7eed7666d4a240fd3fa7390e3450397.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[tox-dev/tox-pyenv](https://github.com/tox-dev/tox-pyenv)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
