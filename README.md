# Repolex Knowledge Graph of allenai/sensitivity-estimate

RDF knowledge graph data for [allenai/sensitivity-estimate](https://github.com/allenai/sensitivity-estimate), parsed by [repolex](https://repolex.ai).

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
rlex download allenai/sensitivity-estimate
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4fb0d6e5fc2a14fdbf5f038f52cd0e1c09f0bad2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4fb0d6e5fc2a14fdbf5f038f52cd0e1c09f0bad2
│           └── chunk-001.nq.gz
├── blob
│   ├── 00c7296883ad58a79b0b41bd6db34897c2ea00b0.nq.gz
│   ├── 0bfb55796f3b7555c838604a8871c1c3ed3f1462.nq.gz
│   ├── 17d0153bf4d5eee89e622a1ead84a407f4d88690.nq.gz
│   ├── 2500e46daef30ffb7c485d518279102f2d84b0ae.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 312ff4f3531478ddbea8bd29979d40aacd42917c.nq.gz
│   ├── 5241113d930ce3c9771cc24a86f679cb6da26caa.nq.gz
│   ├── 5a7081e8df6562293722348334e19825d50991a2.nq.gz
│   ├── 5b522b6b52bf9f56f9ee2117cdaf26097c8ef109.nq.gz
│   ├── 6324d401a069f4020efcf0ff07442724b52f47c2.nq.gz
│   ├── 72ab423ba53af7a34ccd739b2c7ae2b5d29c042c.nq.gz
│   ├── 7e3efcc97271a7903b787eac5f290111447f97fa.nq.gz
│   ├── 8467f869a70681559500d8e66903c73d2ca13fa7.nq.gz
│   ├── 92fe97ff0f83a32d63087d13f5c1fe3e2a0b7f15.nq.gz
│   ├── 95d317d870493b04777d685d68bdd4932931bd4a.nq.gz
│   ├── cd2a0ad62e71b8aaf402a1e643484155ae18059b.nq.gz
│   ├── d47d327cb2af65b93e2603f8d4106325486874e8.nq.gz
│   ├── daebf7b9db133a3666bee4c525d9b8ef2d502fa4.nq.gz
│   ├── dbc203f87ba3bf7d9dc9a0fb173190d014fecea2.nq.gz
│   ├── f15b5a383bbb899cc4fa2f7a9a50a09235d4586d.nq.gz
│   └── fc139879c82dc89d364da56470978302d512a100.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4fb0d6e5fc2a14fdbf5f038f52cd0e1c09f0bad2.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 28 files
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

[allenai/sensitivity-estimate](https://github.com/allenai/sensitivity-estimate)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
