<h1 align="center">Hi there, I'm Huu 👋</h1>

<h3 align="center">Rust Data Engineer · Solana &amp; on-chain data infrastructure</h3>

## About Me

I build streaming data infrastructure in Rust. Most of my work lives where a
firehose of on-chain state meets a database that has to answer questions about
it: gRPC subscriptions, Anchor account decoding, columnar storage, and the
operational plumbing that keeps a pipeline running unattended for weeks.

Right now that means two things. **[klend-indexer](https://github.com/SGDlab67/klend-indexer)**
is a production Rust indexer that subscribes to Kamino Lend account writes over a
Yellowstone gRPC stream, decodes them with Anchor discriminators, and lands them
in ClickHouse. It ran continuously on GCP and accumulated ~1.1M account updates
and ~180K decoded obligation snapshots. Separately, I do network measurement
research at Oregon State University's ASTRO Lab under Dr. Zane Ma, measuring how
much validator identity leaks at Solana's gossip layer.

Solana is the domain I know best, not the boundary. The through-line is Rust and
data engineering.

When I'm not building, you can probably find me analyzing the conceptual
mechanics of Devil Fruits in *One Piece*. [Contact me](#-collab-) if you want to
talk streaming data, Rust, or Solana internals.

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

## Current Projects &amp; Focus

* **[klend-indexer](https://github.com/SGDlab67/klend-indexer):** Rust → Yellowstone gRPC → ClickHouse. Account-level decode, slot-based checkpointing, gap detection, lag metrics, and a freeze/resume runbook so a live pipeline can be parked without losing history.
* **S-NodeFinder:** network measurement research at OSU ASTRO Lab. How much does Solana's gossip layer leak validator identity, and how is that leak weighted by stake and concentrated by cloud provider?
* **Cold-path storage:** Parquet and DataFusion beside ClickHouse, so the same dataset serves both live queries and cheap historical scans.

## 👇 Collab 👇
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/huuforcrypto/)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:taihl.work@gmail.com)


*"The clock is the dataset: a stream you stop observing is history you cannot get back."*
