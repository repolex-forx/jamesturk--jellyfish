# Repolex Knowledge Graph of jamesturk/jellyfish

RDF knowledge graph data for [jamesturk/jellyfish](https://github.com/jamesturk/jellyfish), parsed by [repolex](https://repolex.ai).

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
rlex download jamesturk/jellyfish
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 922a6395d02bc1f405bcd6466252dfdb58225c3f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 922a6395d02bc1f405bcd6466252dfdb58225c3f
│           └── chunk-001.nq.gz
├── blob
│   ├── 04a47a8897f6edfc1fb3c451bc7980f7076dbdd1.nq.gz
│   ├── 0f381cd13d73a32e2229bf3b0fd1d9c9024892c5.nq.gz
│   ├── 22153b3c560144ebc79325661d65e05569cc1c15.nq.gz
│   ├── 2b2c95b519791fec00ddb91d6583451e22186e48.nq.gz
│   ├── 2b769f193e47b7bcc18eeec1748981cf1963bfbf.nq.gz
│   ├── 34ffa0e8ee48efed8e4e5ea92ddfe1bb6bb7fe54.nq.gz
│   ├── 374e1726ca6d048bc87c2febd1a02fae64362c9e.nq.gz
│   ├── 37582bb0f06fd2047d76db5ee0338d075d6018ba.nq.gz
│   ├── 3859973b90431a0137daf8ef079d0ce26347d75d.nq.gz
│   ├── 3864b1108f5678e0399177612fd3ade4bd332307.nq.gz
│   ├── 3e66105ebd52a85f5cb2222c166b779ed42cd12d.nq.gz
│   ├── 3e78b046993e0b6d074683dc70e2cbf69804cdec.nq.gz
│   ├── 4ecbd5281677d2d2a9f63e72547f361a5dfc6d79.nq.gz
│   ├── 4efa9f3a76e83ef52fb5cf0c49ef508bb6287157.nq.gz
│   ├── 550e5525c3fc35accf256e3a8419a910da4e7de1.nq.gz
│   ├── 5d14a9ddf3d0fa9dff5f27c1676b7bbccf4f1b3f.nq.gz
│   ├── 60e1df3ec557c46587dff0713bbfff66898144cb.nq.gz
│   ├── 7ccc655ff331c850ce8c6fd50b3dbb382d6e340b.nq.gz
│   ├── 7f66daa186424b1b3b81cdcd956979d7ddbddc6d.nq.gz
│   ├── 8a047101db23da12c38eb77f29cf2044960461c9.nq.gz
│   ├── 9449e3615845c45ae4b1780b2bc6866a1a027436.nq.gz
│   ├── 95bae45e92653ff1527db95ab65bd190aa25180e.nq.gz
│   ├── 9bb2db4bd38e48aa148a79e661f98712b7125812.nq.gz
│   ├── a51d14cd545cdbcd0c1ad169d8479e1ab3861245.nq.gz
│   ├── bbfa8dde304ee87e827e6c477e9dac5038296b8a.nq.gz
│   ├── bc5020fe5934a3cf941feaee10b3772565f3e491.nq.gz
│   ├── c60bde3c970423bbda2b9d47603f7231f50d78c1.nq.gz
│   ├── c7533a203f40582c649fd05adaa0560eef3e979e.nq.gz
│   ├── c8f9f5ced0a473d628b92317fefcc6c04dec6e99.nq.gz
│   ├── c98361516542494e8260a36c52778e66ebcafb80.nq.gz
│   ├── cfc458de16bc7ec698c287ee807ebde8931f8899.nq.gz
│   ├── dfcf83aa85d217663e912aa03449ed54c5679e21.nq.gz
│   ├── e0c346b0b9b2d4b74cdb1acf0b3e858fc3952da9.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e8668a130a2c8009554e963f974b25d70e2d68f2.nq.gz
│   ├── e91c9dd754f006b8af751b9d76b3c6d04ad47af1.nq.gz
│   ├── f109a0cbd3946a80a8f372e8c6b4aa08832f305f.nq.gz
│   ├── f164cb457d06bfb4aaaac545296a57a3dda95f48.nq.gz
│   └── f8ccf87425bde45fcf4f618c263875cff6f6452c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 922a6395d02bc1f405bcd6466252dfdb58225c3f.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 46 files
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

[jamesturk/jellyfish](https://github.com/jamesturk/jellyfish)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
