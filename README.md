# Repolex Knowledge Graph of docopt/docopt

RDF knowledge graph data for [docopt/docopt](https://github.com/docopt/docopt), parsed by [repolex](https://repolex.ai).

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
rlex download docopt/docopt
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8fea867d4220f1095dae9d6264ec5aa4031fb712
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8fea867d4220f1095dae9d6264ec5aa4031fb712
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b248c96c61eba7e1a163bf57328834d9b9f0778.nq.gz
│   ├── 10472127add76b8432de70c4fb4af7243fbb86f8.nq.gz
│   ├── 23772fd6e0e644023946a7104a6b5e7cf2a38466.nq.gz
│   ├── 2c9e08ae1369896f774f57b44f1104acfc155f8c.nq.gz
│   ├── 322a2ddcfa678151579328f0a33620111179775f.nq.gz
│   ├── 44908944b8c6b942f3405640edd2a7c5eebe474b.nq.gz
│   ├── 463fb5ab75dc01a30fad435fd0b78ccd00ce9396.nq.gz
│   ├── 58ff1bc8e7a072c5dd16eb64a0010d91881938e4.nq.gz
│   ├── 58ffe5e3f9fbd24b915b7e3fd302ef797fd6126d.nq.gz
│   ├── 5d4479f41390d66ddc69399024e8bf18fbe50de6.nq.gz
│   ├── 5e4090017a9bec5de60a745d17007a9e95f31a43.nq.gz
│   ├── 6ae5e96abfcd83a7050a0d98eae0304b5575b69e.nq.gz
│   ├── 6ed43bb7d94603cc19b7bf3fa48b76b1573c5387.nq.gz
│   ├── 820841995015d3e3010c80cfc97b3bdfab55c616.nq.gz
│   ├── 82aa7a918c4d7eb32fc0a0c0d465d863a3ae5970.nq.gz
│   ├── 82df7fdffefc68be9baed5e52bbe363e1d610bb4.nq.gz
│   ├── 8f27e591a18d9888f949b4b5f1437fd96a5d5654.nq.gz
│   ├── 9e337a2d6fe54f5da294ec7a0171143a432172d2.nq.gz
│   ├── a25a9a614fb2fc5fca7be1d3d235117e01c9c866.nq.gz
│   ├── b223172a0e0959374ac4514326f2f369b191592b.nq.gz
│   ├── b7c6281189ac729513000cf5d92d456bb0c1f21f.nq.gz
│   ├── bce7b75996263bca876e9561833a8c7ad5043717.nq.gz
│   ├── bd5f685554da29a681b858e31485f74845ace89f.nq.gz
│   ├── da6af3186d9885023f8edf5877ce27279feddcb7.nq.gz
│   ├── dbc810a23e33da2b0a75068c7aec6bdee630e4b1.nq.gz
│   ├── e80b7b099ea17fb65760d3b35b766cc56e09deee.nq.gz
│   ├── ef75389a51273092a777eb7f698f25105235636d.nq.gz
│   ├── efe9a07f608eb5f62cf4f7d719fffa7bd7443886.nq.gz
│   ├── f5bdc3777ac309f5134d399d9e025f37bce1a573.nq.gz
│   ├── f5e8c7b906d2753e7bdeeb7e483a92384f8cc489.nq.gz
│   └── f97d7bdeb8afd00d4d3bc1c4ae42fc2015c9d0c8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8fea867d4220f1095dae9d6264ec5aa4031fb712.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 39 files
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

[docopt/docopt](https://github.com/docopt/docopt)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
