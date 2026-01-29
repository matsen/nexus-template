# My Nexus

This is a [bipartite](https://github.com/matsen/bipartite) **nexus** — a directory that serves as the central hub for bipartite's various functions:

- **Paper library**: References, knowledge graph edges, and concepts
- **Server configuration**: Remote compute resources for `bip scout`
- **GitHub activity tracking**: Repos and boards for `bip checkin`, `bip digest`
- **Project context**: Background information for AI-assisted workflows

## Quick Start

1. Install [bipartite](https://github.com/matsen/bipartite#installation)
2. Build the search index:
   ```bash
   bip rebuild
   ```
3. Add papers:
   ```bash
   bip s2 add DOI:10.1038/s41586-021-03819-2
   ```
4. Search your library:
   ```bash
   bip search "phylogenetics"
   ```

## Directory Structure

```
my-nexus/
├── .bipartite/           # Cache directory (gitignored, ephemeral)
│   ├── cache/
│   │   └── refs.db       # SQLite FTS index
│   └── vectors.gob       # Embedding vectors
│
├── refs.jsonl            # Paper references (source of truth)
├── edges.jsonl           # Knowledge graph edges
├── concepts.jsonl        # Concept/topic definitions
│
├── servers.yml           # (optional) Remote servers for bip scout
├── sources.json          # (optional) GitHub repos for activity tracking
├── config.json           # (optional) Local paths, API keys
│
├── context/              # (optional) Project context files
└── narrative/            # (optional) Generated digest output
```

## Configuration

Copy the example files and customize for your setup:

```bash
cp servers.yml.example servers.yml
cp sources.json.example sources.json
cp config.json.example config.json
```

See the [bipartite documentation](https://github.com/matsen/bipartite) for configuration details.

## Learn More

- [bipartite CLI reference](https://github.com/matsen/bipartite#commands)
- [Getting started guide](https://github.com/matsen/bipartite/blob/main/docs/guides/getting-started.md)
