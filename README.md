# Repolex Knowledge Graph of coleifer/sweepea

RDF knowledge graph data for [coleifer/sweepea](https://github.com/coleifer/sweepea), parsed by [repolex](https://repolex.ai).

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
rlex download coleifer/sweepea
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8343c97aa125e390e6e4c36de699e48efa0a29d2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8343c97aa125e390e6e4c36de699e48efa0a29d2
│           └── chunk-001.nq.gz
├── blob
│   ├── 00636a5eb5c88512bbe5948107c8cfd33e6f575c.nq.gz
│   ├── 063b1bc5a147e36218394557d2b4cdcb3c1a5e9a.nq.gz
│   ├── 06f957a777f089cf0dd7944dd97d5cf9dba8d04d.nq.gz
│   ├── 08c566257665a7ad74240535873392e49d706f03.nq.gz
│   ├── 1156dae80463fd710d80ea8604d1ba3887d4d7d6.nq.gz
│   ├── 15ab4bc8d4b2d92dd72a67ab4697ce074bbbfaed.nq.gz
│   ├── 3a9944fc794768cafbf2f7e37578896110039cc9.nq.gz
│   ├── 3d84966b2c3544b720b092c09c972d58c6dc733e.nq.gz
│   ├── 5c8192083e28d113ffc4f36a8ee61955dc4e0b8e.nq.gz
│   ├── 5f91405cf01c50f4a0ecc5f550d611e0b7424df2.nq.gz
│   ├── 6502511f66848c51f2f29bf3df4febb476d834cc.nq.gz
│   ├── 65ff78f0c4fcd5827d6c442ec89320503fea5bc0.nq.gz
│   ├── 68ae2b273cecab513ea723459e8ba17b4c7cceff.nq.gz
│   ├── 6ccf1c30863a8558c06e6722c75e5ff9c116b9af.nq.gz
│   ├── 79e98e791adfcb664d40458b5da272de9d591b31.nq.gz
│   ├── 8ad5f83b4c483f1b0d161082b86c27e316de19a1.nq.gz
│   ├── 9be4e21bff4d89a425bd0e902edfe40bcf0470fb.nq.gz
│   ├── a3e93288def0c8c0e7d9f08291bbf1fbf864ea94.nq.gz
│   ├── a4988854a1174250184ee280d26d088edbf69070.nq.gz
│   ├── a7b46d5a9d8b7c4dad6b1c9f3db4b5368abdf721.nq.gz
│   ├── c0d5f634ba2e5ae4d5db9861e385ed8a840795ec.nq.gz
│   ├── c752ab3ead2e7be324e5cafb5e1d53135c16af13.nq.gz
│   ├── d30c30b002633894a3067f1da561ba8f737f5db2.nq.gz
│   ├── d35c13f9ac95d9d88183b19039dcf3e0e7d8f598.nq.gz
│   ├── dc3e485e73d046b4d92087f73d886be75a39726a.nq.gz
│   ├── e767d7d76377ccdee1ef857861e12d645e0c1836.nq.gz
│   └── ecf39f275acea874cc0e063aca20fb1c61ba1a2b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8343c97aa125e390e6e4c36de699e48efa0a29d2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 35 files
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

[coleifer/sweepea](https://github.com/coleifer/sweepea)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
