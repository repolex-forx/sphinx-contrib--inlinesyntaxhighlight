# Repolex Knowledge Graph of sphinx-contrib/inlinesyntaxhighlight

RDF knowledge graph data for [sphinx-contrib/inlinesyntaxhighlight](https://github.com/sphinx-contrib/inlinesyntaxhighlight), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/inlinesyntaxhighlight
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 216b874c1ff0abf150245b1cad354caf2d8e90c6
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 216b874c1ff0abf150245b1cad354caf2d8e90c6
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d2519be55cce0b9d32c62fbfccacecaba5ae272.nq.gz
│   ├── 8a19a1b556bcc63c99ce84d8ae3264fd05179867.nq.gz
│   ├── 926cc7b14c1ecdca8d3c7ae299350d98a3f9c905.nq.gz
│   ├── a88698557f2673f764eb68ff57f42ed26ba37f75.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── bfb9f4b5e992f8af7ca8153e93dab5c67e47976f.nq.gz
│   ├── d75b62ba8bc13b12967fc94cd7d0785130bf1f30.nq.gz
│   ├── e57163a51838a102dea8ad451402bc8ef4367a45.nq.gz
│   ├── f52970ee6db42c94728afa6858ebc9a778642285.nq.gz
│   ├── f5db519df5a0b18b665d9fe8d802e639a88092bc.nq.gz
│   └── f99f9920f44a352d180a79a3df121381b92e4a07.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 216b874c1ff0abf150245b1cad354caf2d8e90c6.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 17 files
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

[sphinx-contrib/inlinesyntaxhighlight](https://github.com/sphinx-contrib/inlinesyntaxhighlight)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
