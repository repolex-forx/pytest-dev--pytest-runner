# Repolex Knowledge Graph of pytest-dev/pytest-runner

RDF knowledge graph data for [pytest-dev/pytest-runner](https://github.com/pytest-dev/pytest-runner), parsed by [repolex](https://repolex.ai).

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
rlex download pytest-dev/pytest-runner
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9d13da8bd36ecd9634629b492315cb28eff44183
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9d13da8bd36ecd9634629b492315cb28eff44183
│           └── chunk-001.nq.gz
├── blob
│   ├── 190b3551e5648512409f243755bbad97920c2b64.nq.gz
│   ├── 21142b52a3cc515ef0a6b7bb6429d660a9a6febc.nq.gz
│   ├── 353924be0e59b9ad7e6c22848c2189398481821d.nq.gz
│   ├── 3944ba91f2bdc6d32421b214b25b75a006d9b9d9.nq.gz
│   ├── 3b4273aa46d3966b4404ee19c68a7944356a9c66.nq.gz
│   ├── 3ca2af38b1c016e5454e4be9751e8f829c7629e8.nq.gz
│   ├── 41192fa83ea9f3194d5a31f429e7fd5515c7529d.nq.gz
│   ├── 48b2e246f1b40ddbe34618a616a51554d109c0e3.nq.gz
│   ├── 5424298dd3133c7cddd74ad9f2a11cb4f60b4048.nq.gz
│   ├── 6a34e662d391e5d273f91eac3c0a6983ed7d718f.nq.gz
│   ├── 80e98cc96c6a403cd211538e494e9765722b3f17.nq.gz
│   ├── 89ff33961ba3d6f9cda89322a1fdbf1ac2e35513.nq.gz
│   ├── 8e217503ba1a68826af8e1e9db4bd16ce7a21857.nq.gz
│   ├── 976ba0294638950e865be3934cbeee3b6305ffd6.nq.gz
│   ├── a9aff9d1ca9a9215750ecdc40803b2ebf68e6a97.nq.gz
│   ├── b8aeea177b3869aaf7cfcdc1b8b272fee9c202e6.nq.gz
│   ├── cc698548db4fa194439c2da704e1d4c342ef4200.nq.gz
│   ├── d2e3fddd2eb2ed850624d32f47b346c8e7cf3b72.nq.gz
│   ├── d5eab1be5c2415b0e9bb1542938bdd892d975c19.nq.gz
│   ├── edf6f55f9b23a87abfcfab2a4b9d2f96b15e526e.nq.gz
│   └── fc2eb829219848bcb4c5e9cc64f3816e694826d5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9d13da8bd36ecd9634629b492315cb28eff44183.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[pytest-dev/pytest-runner](https://github.com/pytest-dev/pytest-runner)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
