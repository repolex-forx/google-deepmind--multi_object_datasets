# Repolex Knowledge Graph of google-deepmind/multi_object_datasets

RDF knowledge graph data for [google-deepmind/multi_object_datasets](https://github.com/google-deepmind/multi_object_datasets), parsed by [repolex](https://repolex.ai).

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
rlex download google-deepmind/multi_object_datasets
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a32c3bcbb4c75cb7243894d45fb6f226cd906f65
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a32c3bcbb4c75cb7243894d45fb6f226cd906f65
│           └── chunk-001.nq.gz
├── blob
│   ├── 157b6ab3508370796ac0010648f529b2af6f285f.nq.gz
│   ├── 31d3ed547a9b76a2f72a126b3d3ac8a7fe56d5df.nq.gz
│   ├── 3cbf80e838383fd4d905f58127034200af390177.nq.gz
│   ├── 7deda1e7a23aec0ad008475df8e40d7e15a4870f.nq.gz
│   ├── 807beec0630081980dae807d4b2f918a018578f2.nq.gz
│   ├── 8187242b1f23f9ae054e5220826eda2f404b7ccf.nq.gz
│   ├── b14f7b207dc6023b6456b8b41f665137e2277bcf.nq.gz
│   ├── db177d4ac70f76c2172ce65ca33c830d6cbd3ac5.nq.gz
│   ├── ddc2cf64449593cfb0cf3e1a6a8d1d542d6b295f.nq.gz
│   ├── e2fad58aab4c9c85d12339ae2d84fcd3b7dd109c.nq.gz
│   └── ef65f4bda220cda548ca43b28cea51fcbd04bd40.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a32c3bcbb4c75cb7243894d45fb6f226cd906f65.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[google-deepmind/multi_object_datasets](https://github.com/google-deepmind/multi_object_datasets)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
