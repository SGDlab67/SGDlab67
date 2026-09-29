# Huu

Rust data engineer. Solana and on-chain data infrastructure.

## About

I build streaming data infrastructure in Rust. Most of my work sits where a
firehose of on-chain state meets a database that has to answer questions about
it: gRPC subscriptions, Anchor account decoding, columnar storage, and the
plumbing that keeps a pipeline running unattended for weeks.

**[klend-indexer](https://github.com/SGDlab67/klend-indexer)** is the longest
running piece of that. It subscribes to Kamino Lend account writes over a
Yellowstone gRPC stream, decodes them with Anchor discriminators, and lands
them in ClickHouse. On GCP it accumulated roughly 1.1M account updates and
180K decoded obligation snapshots. It's frozen now, on purpose: Yellowstone
can't re-serve old slots, so the history was exported to Parquet before the
stream was stopped. Designing around that one constraint taught me more than
the rest of the pipeline did.

**[karat67](https://github.com/SGDlab67/karat67)** came out of running that
thing. An indexer can pass every freshness and throughput check while writing
empty or malformed rows, and every dashboard built on top inherits the error.
karat67 checks indexed data against the chain itself: account shape against
the IDL, byte-level reconciliation of sampled accounts, and slot completeness
against `getBlocks` (skipped slots aren't gaps, which is the part people get
wrong). Freshness and liveness are deliberately out of scope. Every indexer
already has those.

I also do network measurement research at Oregon State's ASTRO Lab under
Dr. Zane Ma, on how much validator identity leaks at Solana's gossip layer
and how that leak is weighted by stake and concentrated by cloud provider.

Solana is the domain I know best. What sits underneath it is Rust and data
engineering, and that part travels.

Off the clock I argue about the conceptual mechanics of Devil Fruits in
*One Piece*.

## Skills

### Data &amp; Systems
[![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)](https://www.rust-lang.org/)
[![ClickHouse](https://img.shields.io/badge/ClickHouse-FFCC01?style=for-the-badge&logo=clickhouse&logoColor=black)](https://clickhouse.com/)
[![Apache Arrow](https://img.shields.io/badge/Arrow%20%2F%20Parquet-1B1F23?style=for-the-badge&logo=apache&logoColor=white)](https://arrow.apache.org/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![Google Cloud](https://img.shields.io/badge/GCP-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white)](https://cloud.google.com/)

### Blockchain &amp; Web3
[![Solana](https://img.shields.io/badge/Solana-14F195?style=for-the-badge&logo=solana&logoColor=black)](https://solana.com/)
[![Anchor](https://img.shields.io/badge/Anchor-2E4BFF?style=for-the-badge&logoColor=white)](https://www.anchor-lang.com/)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)

### Also in the toolbox
[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org)
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org)
[![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)](https://www.linux.org/)
[![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)](https://git-scm.com/)

## What I'm working on

* **[karat67](https://github.com/SGDlab67/karat67):** integrity checks for
  Solana indexers, as a Rust crate and a `karat` CLI. Three checks (shape,
  reconciliation, completeness), JSON output, built to drop into CI next to
  an existing pipeline. This is the active one.
* **[klend-indexer](https://github.com/SGDlab67/klend-indexer):** Rust to
  Yellowstone gRPC to ClickHouse. Account-level decode, slot checkpointing,
  gap detection, lag metrics, and a freeze/resume runbook. Frozen, maintained,
  the dataset lives in Parquet on GCS.
* **S-NodeFinder:** gossip-layer measurement at OSU ASTRO Lab. Collection is
  running, analysis is paused.
* **Cold-path storage:** Parquet and DataFusion beside ClickHouse, so one
  dataset serves live queries and cheap historical scans. Planned, not built.

## Contact

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/huuforcrypto/)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:taihl.work@gmail.com)

Happy to talk streaming data, Rust, or Solana internals.

*"The clock is the dataset: a stream you stop observing is history you cannot get back."*
