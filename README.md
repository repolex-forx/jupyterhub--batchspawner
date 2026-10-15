# Repolex Knowledge Graph of jupyterhub/batchspawner

RDF knowledge graph data for [jupyterhub/batchspawner](https://github.com/jupyterhub/batchspawner), parsed by [repolex](https://repolex.ai).

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
rlex download jupyterhub/batchspawner
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 451dcf171cff7883904845d5de8c5e5e250b64d9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 451dcf171cff7883904845d5de8c5e5e250b64d9
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a3b3eeb41f0ee6a12ad0f17658121aea8d6af47.nq.gz
│   ├── 0dc89813dc10ed07777226c26d348a19ce3afb93.nq.gz
│   ├── 0fe4f7efb208eec7e20ad155d4e642e398d09fb0.nq.gz
│   ├── 15ecf78bbf54cebdf6dd9d97621500f8cfe378b9.nq.gz
│   ├── 246a778090c0aaa0fd1ba743f916d1de5877ace5.nq.gz
│   ├── 33d37d7e7a6fdcfea15195d0bd0ee44200a332ca.nq.gz
│   ├── 34d422b32be4739bf44a2a97afd771877fb05f2b.nq.gz
│   ├── 4c44387de2316b266f24999bd673ecf9005f3771.nq.gz
│   ├── 4e846ebecb8748bc3e04bd411c2e09958cbc6c01.nq.gz
│   ├── 56fc7798d4db85d70f557fc424d4f82a6be49aac.nq.gz
│   ├── 7d43f806355e73a2b9a55409471bb65a69afe467.nq.gz
│   ├── 809d308f443af960e17447f1e49138a374fc1991.nq.gz
│   ├── 866bf51068fb7f838b5f51bdeecbd00175ad2626.nq.gz
│   ├── 8e6c3273b9ef8a299eafe1f53ece997153e5ef23.nq.gz
│   ├── 992f2c3448a9ef28015a06084b729664e5749c85.nq.gz
│   ├── a7941d6cebf500cba053211bd178de8faea7c20f.nq.gz
│   ├── b0863e54053ae7b3c2beeec21af83a8fe26d423a.nq.gz
│   ├── b8bff1ae791279357974f56eb6d9359eab676229.nq.gz
│   ├── d7aaadcdc87d90ca80598e8ef773dcd990df4df0.nq.gz
│   ├── e5d43c0994e92e9ce43847178007e4e23ef979d8.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e91831ce3a6407815bbcd7a6c8b132fa3abf7c51.nq.gz
│   └── f113d728a15f84a89ac0a5fd443830e8b9d8a651.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 451dcf171cff7883904845d5de8c5e5e250b64d9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[jupyterhub/batchspawner](https://github.com/jupyterhub/batchspawner)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
