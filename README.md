# Repolex Knowledge Graph of matplotlib/mpl-finance

RDF knowledge graph data for [matplotlib/mpl-finance](https://github.com/matplotlib/mpl-finance), parsed by [repolex](https://repolex.ai).

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
rlex download matplotlib/mpl-finance
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d80c814a4c4fd74d679a7767aa752d8cb4e49cd7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d80c814a4c4fd74d679a7767aa752d8cb4e49cd7
│           └── chunk-001.nq.gz
├── blob
│   ├── 1415edb410b9f9059fab7d402ed2ff4db35bd1e8.nq.gz
│   ├── 2423f3b185add7c947038bc2ca0f8623888cefa7.nq.gz
│   ├── 2768e5f857493cdfd55a209c26711171aa5cb6b4.nq.gz
│   ├── 32edb395b09d4029f353558d9f496080e8eab652.nq.gz
│   ├── 3b9c3d1c9abb2221162d0e5a1d70ec7b2e75f152.nq.gz
│   ├── 52e8c63b68c84962f4032415dcd3dd65a3229026.nq.gz
│   ├── 64a000a6b947cc6be960401e00b7252950b1ca7b.nq.gz
│   ├── 71da9bbf1a043cb34c8757a410300b0d1f318c68.nq.gz
│   ├── 74e947b2752e41859c0294222aa85c0399e729ad.nq.gz
│   ├── 846eb456e23dae61beb5228f438f5a2550177045.nq.gz
│   ├── a6d0a3a262d9520b226f56a4bc5367a080d78297.nq.gz
│   ├── b8454c6a23e47fa7470b42536499f576eceec308.nq.gz
│   ├── bb8a341f30bd9ea5f599b2338a71524af22059d5.nq.gz
│   ├── beb04431cf3e693906a42160001968bec1b6fd74.nq.gz
│   ├── c6c4916b9d43c5a81007305567b2b59e1ec1eb10.nq.gz
│   ├── c876859194a12f0cb143518cf7a4df7928b37421.nq.gz
│   ├── d0f6749667a9fed24527082ed10cfe11da0f9b6b.nq.gz
│   ├── d704446d5b738354f3ac29ac12850f3795190dd5.nq.gz
│   ├── d8ead5f0dfc0a740559ebbda332285a0f378e539.nq.gz
│   ├── da0db501f4159536717d1bc9bd9f10500c211a40.nq.gz
│   ├── e0f28368c9ce2ca38b5747b7dff2c6a07f4bb363.nq.gz
│   └── e2beda099c49c1258741e88934053a019cc22a22.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d80c814a4c4fd74d679a7767aa752d8cb4e49cd7.nq.gz
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

[matplotlib/mpl-finance](https://github.com/matplotlib/mpl-finance)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
