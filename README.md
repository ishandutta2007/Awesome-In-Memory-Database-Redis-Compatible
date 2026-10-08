# Awesome-In-Memory-Database-Redis-Compatible

# Top In-Memory Database (Redis-Compatible) Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Managed Redis, In-Memory Key-Value Stores & Self-Hosted Alternatives*  
**Last updated: October 2026**

This repository tracks notable **commercial managed Redis platforms** and **open-source projects** that provide in-memory key-value storage — from fully managed cloud services to community-driven forks and high-performance alternatives.

**Examples** include Amazon MemoryDB for Redis, Redis Enterprise Cloud, Upstash Redis, Dragonfly Cloud, Momento Serverless Cache, KeyDB Cloud, Azure Cache for Redis, Google Cloud Memorystore, Aiven for Redis, and Hazelcast Cloud (the category leaders).

**Open-source emphasis**: The Redis ecosystem underwent a major shift in 2024 when Redis Inc. moved to SSPL and then AGPLv3 licensing, prompting the creation of **Valkey** as a Linux Foundation fork under BSD-3-Clause . **KeyDB** and **Dragonfly** offer multi-threaded alternatives with different performance characteristics . **Garnet** from Microsoft Research brings .NET-native Redis compatibility . **DiceDB**, **tinyredis**, and **SugarDB** provide additional open-source options. This section is heavily expanded.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Amazon MemoryDB for Redis](https://aws.amazon.com/memorydb/)**  
  **AWS's durable in-memory database** — Redis-compatible with microsecond read and single-digit millisecond write latency . **Multi-AZ durability with transaction log** . **Best for AWS-native applications requiring durable in-memory storage** . **Note**: AWS now defaults new ElastiCache and MemoryDB clusters to **Valkey** unless explicitly overridden .

- **[Redis Enterprise Cloud](https://redis.com/cloud/)**  
  **The commercial Redis platform** — fully managed with active-active geo-distribution and modules . **Pricing scales with throughput and memory** . **Best for enterprises wanting Redis with commercial support** . **Note**: Redis 8 is now available under AGPLv3 as an additional licensing option .

- **[Upstash Redis](https://upstash.com/redis)**  
  **Serverless Redis** — pay-per-request pricing with global replication . **REST API and low latency** . **Best for serverless applications** .

- **[Dragonfly Cloud](https://www.dragonflydb.io/)**  
  **Managed Dragonfly** — multi-threaded architecture for 25x throughput over single-threaded engines . **Best for high-performance caching** . **Note**: Dragonfly uses BSL 1.1 with additional use grant for production use .

- **[Momento Serverless Cache](https://www.gomomento.com/)**  
  **Serverless caching platform** — pay-per-use with sub-millisecond latency . **Best for serverless architectures** .

- **[KeyDB Cloud](https://keydb.dev/)**  
  **Managed KeyDB** — multi-threaded Redis fork with active-active replication . **Best for high-throughput workloads** .

- **[Azure Cache for Redis](https://azure.microsoft.com/en-us/products/cache/)**  
  **Microsoft's managed Redis** — integrated with Azure ecosystem . **Note**: Microsoft has announced retirement of Azure Cache for Redis: Enterprise tiers on 31 March 2027, Basic/Standard/Premium on 30 September 2028. Migration to **Azure Managed Redis** is the destination .

- **[Google Cloud Memorystore](https://cloud.google.com/memorystore)**  
  **Google's managed Redis** — fully managed with GCP integration . **Supports Valkey** as a managed option .

- **[Aiven for Redis](https://aiven.io/redis)**  
  **Managed Redis on multiple clouds** — available on AWS, GCP, Azure, and DigitalOcean . **Best for multi-cloud Redis** .

- **[Hazelcast Cloud](https://hazelcast.com/)**  
  **In-memory data grid** — distributed caching and computing . **Best for distributed caching at scale** .

## Open-Source GitHub Projects

### Redis Forks & Successors

- **[Valkey](https://github.com/valkey-io/valkey)**  
  **The primary community-driven open-source successor to Redis**, BSD-3-Clause licensed . **Linux Foundation project backed by AWS, Google, and Oracle** . **Fully free with no license restrictions** . **Retains Redis core data structures, persistence, replication, Sentinel, clustering, Lua scripting, and transactions** — existing Redis clients can connect directly . **Valkey 8.0 introduced enhanced I/O multithreading** with reports of up to 1.19 million requests per second . **Provides BSD-licensed equivalents to Redis Stack modules**: valkey-json, valkey-bloom, valkey-search, valkey-ldap . **Best for organizations requiring permissive licensing and community governance** .

- **[Redis 8](https://github.com/redis/redis)**  
  **Redis under AGPLv3 licensing** (additional option alongside RSALv2/SSPLv1), with Redis Stack modules integrated into core . **Significant performance improvements**: up to 87% faster commands and 2x throughput over earlier releases . **Includes JSON, Time Series, probabilistic data types, and Query Engine** . **Best for teams needing Redis Stack modules under open-source licensing** .

### High-Performance Alternatives

- **[Dragonfly](https://github.com/dragonflydb/dragonfly)**  
  **Modern ultra-fast in-memory data store**, BSL 1.1 licensed with additional use grant . **Multi-threaded, shared-nothing architecture** — partitions keyspace between threads for vertical scaling . **Consistently delivered 2.5–3.5x ops/sec of original Redis under high concurrency** . **Memory efficiency: same data used 15–22% less RAM** . **Supports Redis and Memcached APIs, snapshots, replication, expiry, and eviction** . **Best for memory or CPU-constrained workloads requiring maximum performance per dollar** .

- **[KeyDB](https://github.com/Snapchat/KeyDB)**  
  **Multi-threaded Redis fork from Snapchat**, BSD-3-Clause licensed . **Multithreaded networking and query processing** leveraging multiple CPU cores . **Active-active replication** — multiple instances can accept writes and replicate to each other . **FLASH storage for large datasets and subkey expiration** . **Trade-off**: Slower development cadence than Valkey, Redis, or Dragonfly . **Best for active-active replication requirements** .

- **[Garnet](https://github.com/microsoft/garnet)**  
  **Microsoft Research's Redis-compatible implementation**, MIT licensed . **Built on modern .NET runtime with native multithreading and lock-free data structures** . **Async-optimized network I/O and minimal garbage collection overhead** . **Trade-off**: Only ~70% Redis API compatibility — migration requires command-by-command review . **Best for .NET-centric environments** .

### Redis-Compatible Implementations

- **[DiceDB](https://github.com/DiceDB/dice)**  
  **In-memory real-time database with SQL-based reactivity**, fork of Valkey . **Drop-in replacement for Redis** — fully compatible with Valkey and Redis tooling . **dicedb-spill module**: transparently persists evicted keys to disk using RocksDB and restores them on cache misses . **Best for real-time applications needing cache spill to disk** .

- **[tinyredis](https://github.com/HSn0918/tinyredis)**  
  **Redis-compatible cache server written in Go**, open-source . **RESP protocol compatibility** — works with redis-cli, Medis, AnotherRedisDesktopManager . **Raft-based clustering** with automatic leader election and log replication . **In-memory data structures covering strings, hashes, lists, sets, sorted sets, TTL** . **Best for Go-based Redis-compatible server with Raft clustering** .

- **[SugarDB](https://github.com/EchoVault/SugarDB)**  
  **Embeddable and distributed in-memory alternative to Redis**, Apache-2.0 licensed with **498 GitHub stars** . **Go-based with LFU/LRU caching, pub/sub, and cluster support** . **Best for embedded Go applications** .

### Additional Strong Open-Source Options

- **Memcached** — Classic distributed memory object caching system, BSD-licensed .
- **Apache Ignite** — Distributed in-memory computing platform with persistence .
- **Hazelcast** — Unified real-time data platform combining stream processing with fast data store .
- **BuntDB** — Embeddable in-memory key/value database for Go .
- **Ristretto** — In-memory cache library for Go with LRU, LFU, ARC eviction .

**Frameworks for building custom in-memory database solutions**: Combine **Valkey** for the safest permissively-licensed Redis replacement with full command compatibility . Use **Dragonfly** when vertical scaling and multi-core utilization are the primary goals . Deploy **KeyDB** for active-active replication requirements . Choose **Redis 8** when Redis Stack modules are essential and AGPLv3 is acceptable . Integrate **Garnet** for .NET-centric environments with partial Redis API needs . Use **DiceDB** for cache spill-to-disk capabilities . Note that managed in-memory databases with global infrastructure, automatic scaling, and vendor-supported SLAs (Amazon MemoryDB, Redis Enterprise Cloud, Azure Cache for Redis) remain primarily commercial territory; open-source stacks provide strong in-memory storage, caching, and persistence foundations that require integration for complete managed deployments.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- In-memory databases handle sensitive application data. Self-hosted solutions require proper security hardening, access controls, encryption at rest and in transit, and compliance with data privacy regulations.
- **License considerations**: Valkey uses BSD-3-Clause , Redis 8 uses AGPLv3/RSALv2/SSPLv1 , Dragonfly uses BSL 1.1 , KeyDB uses BSD-3-Clause , and Garnet uses MIT . Verify licensing against your use case before committing.
- **Redis API compatibility varies**: Valkey ~100% , KeyDB ~95% , Garnet ~70% . Module dependencies (Redis Stack, custom modules) are the most common migration blocker — check before committing to a fork .
- **Azure Cache for Redis retirement**: Enterprise tiers retire 31 March 2027; Basic/Standard/Premium retire 30 September 2028. Migration to Azure Managed Redis is the destination .
- The open-source ecosystem provides strong in-memory storage, caching, and persistence foundations, but **managed infrastructure, global scale, and vendor-supported SLAs** remain primarily commercial offerings.

---

**Made for platform engineers, application developers, and organizations seeking in-memory database sovereignty.**  
Let's make in-memory databases more open, transparent, and performant.
