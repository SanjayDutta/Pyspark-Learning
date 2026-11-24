# PySpark — Data Engineering Masterclass

> Living curriculum | 12 weeks | 8–10 hours/week | Junior–intermediate interview target

## How to use this file

- Mark `[x]` only after explaining the concept independently and completing its relevant exercise.
- Update the weekly status, evidence, and open questions after each lesson.
- Keep this file in your ChatGPT Project and/or Git repository. Replace the project copy after updates; the downloaded file is not automatically synchronized.
- Suggested weekly allocation: 3 hours theory, 3–4 hours labs, 1–2 hours review/interview practice, 1 hour documentation.
- Pace is flexible; do not advance just to meet a calendar deadline.

## Master progress

| Week | Focus | Status |
| :--- | :--- | :--- |
| 1 | Distributed computing from first principles | Not started |
| 2 | Spark architecture and cluster setup | Not started |
| 3 | Execution model and fault tolerance | Not started |
| 4 | Spark SQL, Catalyst and partitioning | Not started |
| 5 | Shuffle and distributed aggregation | Not started |
| 6 | Distributed joins and data skew | Not started |
| 7 | Memory and resource management | Not started |
| 8 | Caching, AQE and performance debugging | Not started |
| 9 | Distributed storage and file optimization | Not started |
| 10 | Delta Lake, Databricks and advanced batch processing | Not started |
| 11 | Structured Streaming and production pipelines | Not started |
| 12 | Production engineering, capstone and interviews | Not started |

## Learning method

For each lesson: understand the problem → understand the mechanism → predict execution → implement → observe metrics → introduce a controlled failure or optimization → answer interview questions.

## Detailed weekly syllabus

### Week 1 — Distributed computing from first principles

**Status:** Not started

#### 1.1 Computing fundamentals

- [ ] CPU cores, threads and processes
- [ ] Sequential vs concurrent vs parallel execution
- [ ] CPU-bound vs I/O-bound workloads
- [ ] RAM, disk and network bottlenecks

#### 1.2 Distributed systems

- [ ] Big Data and 3Vs
- [ ] Vertical vs horizontal scaling
- [ ] Partitioning data
- [ ] Data locality
- [ ] Coordination and communication
- [ ] Partial failures and retries

#### 1.3 Manual distributed aggregation

- [ ] Split transactions across machines
- [ ] Local partial aggregation
- [ ] Combine results
- [ ] Handle repeated keys
- [ ] Reason about network cost
- [ ] Compare Pandas and Spark

**Practical lab**

- [ ] Implement sequential and multiprocessing aggregation; manually simulate four workers and a failed task.

**Interview checkpoint**

- [ ] Explain why four machines do not guarantee 4x speedup and when Spark is unnecessary.

**Completion and evidence**

- [ ] Explain the core mechanisms without notes.
- [ ] Save code, observations and relevant execution plans or metrics.
- [ ] Complete interview checkpoint and revisit weak areas.
- **Date completed:**
- **Evidence / notebook / commit:**
- **Open questions / topics to revisit:**

---

### Week 2 — Spark architecture and cluster setup

**Status:** Not started

#### 2.1 Components

- [ ] Driver
- [ ] SparkSession and SparkContext
- [ ] Worker nodes
- [ ] Executors
- [ ] Cluster manager
- [ ] JVM and Python workers
- [ ] Py4J in classic PySpark

#### 2.2 Deployment

- [ ] Local mode and `local[N]`
- [ ] Standalone, YARN and Kubernetes
- [ ] Client vs cluster deploy mode and manager-specific support
- [ ] `spark-submit`
- [ ] Application lifecycle

#### 2.3 Cluster laboratory

- [ ] Install compatible Java and Spark
- [ ] Local Spark UI
- [ ] Docker master and two workers
- [ ] Executor cores and memory
- [ ] Shared storage
- [ ] Driver and executor connectivity
- [ ] Optional physical or Azure cluster

**Practical lab**

- [ ] Run the same job locally and on two worker containers; verify executor placement in UI; optionally use separate hosts with private networking and shared storage.

**Interview checkpoint**

- [ ] Explain worker vs executor vs driver, and how a submitted program reaches multiple machines.

**Completion and evidence**

- [ ] Explain the core mechanisms without notes.
- [ ] Save code, observations and relevant execution plans or metrics.
- [ ] Complete interview checkpoint and revisit weak areas.
- **Date completed:**
- **Evidence / notebook / commit:**
- **Open questions / topics to revisit:**

---

### Week 3 — Execution model and fault tolerance

**Status:** Not started

#### 3.1 Abstractions

- [ ] RDDs and DataFrames
- [ ] Schemas
- [ ] Transformations vs actions
- [ ] Lazy evaluation
- [ ] Narrow vs wide dependencies

#### 3.2 Scheduling

- [ ] DAGs
- [ ] Applications, jobs, stages and tasks
- [ ] Stage boundaries
- [ ] Task slots
- [ ] Pipelining
- [ ] Scheduling and retries

#### 3.3 Recovery

- [ ] RDD lineage
- [ ] Lost partitions
- [ ] Executor loss
- [ ] Task retries
- [ ] Checkpointing introduction
- [ ] Limits of driver recovery

**Practical lab**

- [ ] Predict stages for filter and aggregation; inspect Jobs and Stages tabs; stop a worker in an isolated lab and observe recovery.

**Interview checkpoint**

- [ ] Explain how an action triggers execution and why a shuffle creates a stage boundary.

**Completion and evidence**

- [ ] Explain the core mechanisms without notes.
- [ ] Save code, observations and relevant execution plans or metrics.
- [ ] Complete interview checkpoint and revisit weak areas.
- **Date completed:**
- **Evidence / notebook / commit:**
- **Open questions / topics to revisit:**

---

### Week 4 — Spark SQL, Catalyst and partitioning

**Status:** Not started

#### 4.1 SQL engine

- [ ] DataFrame API vs SQL
- [ ] Temporary and global temporary views
- [ ] Catalogs and tables
- [ ] Analyzed, optimized and physical plans
- [ ] Catalyst
- [ ] Tungsten and whole-stage code generation

#### 4.2 Python execution

- [ ] Built-in expressions vs Python UDFs vs Pandas UDFs
- [ ] Serialization and Arrow
- [ ] `explain` extended, formatted and cost

#### 4.3 Partitions

- [ ] Input, runtime, shuffle and storage partitions
- [ ] Task parallelism
- [ ] Hash and range partitioning
- [ ] `repartition` vs `coalesce`
- [ ] Partition sizing
- [ ] Inspect partition distribution

**Practical lab**

- [ ] Compare SQL and DataFrame plans; benchmark built-ins vs UDFs; vary partitions and cores; inspect partition counts.

**Interview checkpoint**

- [ ] Explain how Spark optimizes queries and why adding cores may not improve a stage.

**Completion and evidence**

- [ ] Explain the core mechanisms without notes.
- [ ] Save code, observations and relevant execution plans or metrics.
- [ ] Complete interview checkpoint and revisit weak areas.
- **Date completed:**
- **Evidence / notebook / commit:**
- **Open questions / topics to revisit:**

---

### Week 5 — Shuffle and distributed aggregation

**Status:** Not started

#### 5.1 Shuffle mechanics

- [ ] Why keys must be colocated
- [ ] Map-side partial aggregation
- [ ] Hash redistribution
- [ ] Shuffle write and read
- [ ] Network transfer
- [ ] Serialization
- [ ] Shuffle files

#### 5.2 Costs and boundaries

- [ ] Exchange operators
- [ ] Disk I/O
- [ ] Spill vs shuffle
- [ ] Shuffle partition configuration
- [ ] Fetch failures
- [ ] Narrow vs wide operations

#### 5.3 Experiments

- [ ] `filter` vs `groupBy`
- [ ] `distinct`
- [ ] `orderBy`
- [ ] `repartition`
- [ ] Compare shuffle metrics
- [ ] Identify unnecessary exchanges

**Practical lab**

- [ ] Trace customer aggregation by hand; measure shuffle read/write in Spark UI; compare multiple shuffle partition counts.

**Interview checkpoint**

- [ ] Explain what moves during a shuffle, why it is expensive and how to reduce it.

**Completion and evidence**

- [ ] Explain the core mechanisms without notes.
- [ ] Save code, observations and relevant execution plans or metrics.
- [ ] Complete interview checkpoint and revisit weak areas.
- **Date completed:**
- **Evidence / notebook / commit:**
- **Open questions / topics to revisit:**

---

### Week 6 — Distributed joins and data skew

**Status:** Not started

#### 6.1 Join semantics

- [ ] Inner, outer, semi and anti joins
- [ ] Null semantics
- [ ] Duplicate keys and cardinality explosion

#### 6.2 Physical joins

- [ ] Broadcast hash join
- [ ] Sort-merge join
- [ ] Shuffled hash join
- [ ] Broadcast nested-loop and Cartesian joins
- [ ] Build/probe
- [ ] Join hints
- [ ] Thresholds and statistics

#### 6.3 Skew

- [ ] Hot keys
- [ ] Uneven partitions
- [ ] Stragglers
- [ ] Salting
- [ ] Pre-aggregation
- [ ] Skew-aware strategies
- [ ] Limitations of repartitioning by the same hot key

**Practical lab**

- [ ] Join orders and customers using different strategies; verify plans; inject a hot key; measure skew and compare remedies.

**Interview checkpoint**

- [ ] Choose a join for large-small and large-large tables; diagnose one slow task.

**Completion and evidence**

- [ ] Explain the core mechanisms without notes.
- [ ] Save code, observations and relevant execution plans or metrics.
- [ ] Complete interview checkpoint and revisit weak areas.
- **Date completed:**
- **Evidence / notebook / commit:**
- **Open questions / topics to revisit:**

---

### Week 7 — Memory and resource management

**Status:** Not started

#### 7.1 Memory model

- [ ] Driver vs executor memory
- [ ] JVM heap
- [ ] Execution and storage memory
- [ ] Unified memory
- [ ] Off-heap and overhead
- [ ] Python worker memory

#### 7.2 Failure modes

- [ ] Garbage collection
- [ ] Disk spill
- [ ] Driver OOM from `collect`
- [ ] Executor OOM
- [ ] Oversized partitions and broadcasts

#### 7.3 Resource sizing

- [ ] Executor cores and memory
- [ ] Driver sizing
- [ ] Task concurrency
- [ ] Dynamic allocation
- [ ] Broadcast variables vs broadcast joins
- [ ] Accumulators and retry caveats

**Practical lab**

- [ ] Inspect memory and GC metrics; safely reproduce bounded memory pressure in a disposable environment; compare configurations.

**Interview checkpoint**

- [ ] Diagnose driver vs executor OOM and explain why adding memory is not always the answer.

**Completion and evidence**

- [ ] Explain the core mechanisms without notes.
- [ ] Save code, observations and relevant execution plans or metrics.
- [ ] Complete interview checkpoint and revisit weak areas.
- **Date completed:**
- **Evidence / notebook / commit:**
- **Open questions / topics to revisit:**

---

### Week 8 — Caching, AQE and performance debugging

**Status:** Not started

#### 8.1 Reuse

- [ ] `cache` and `persist`
- [ ] Storage levels
- [ ] Lazy materialization
- [ ] Eviction
- [ ] `unpersist`
- [ ] Checkpoint vs cache
- [ ] Costs of caching

#### 8.2 AQE

- [ ] Runtime statistics
- [ ] Shuffle partition coalescing
- [ ] Adaptive join selection
- [ ] Skew join handling
- [ ] Inspect initial and final plans

#### 8.3 Debugging workflow

- [ ] Spark UI Jobs, Stages, SQL, Executors and Storage
- [ ] Task duration distributions
- [ ] Shuffle, spill, GC and input metrics
- [ ] Event logs and History Server
- [ ] Controlled benchmarking

**Practical lab**

- [ ] Compare repeated queries with and without caching; compare AQE on/off; diagnose a deliberately slow pipeline using evidence.

**Interview checkpoint**

- [ ] Explain when caching hurts and how to investigate a slow job systematically.

**Completion and evidence**

- [ ] Explain the core mechanisms without notes.
- [ ] Save code, observations and relevant execution plans or metrics.
- [ ] Complete interview checkpoint and revisit weak areas.
- **Date completed:**
- **Evidence / notebook / commit:**
- **Open questions / topics to revisit:**

---

### Week 9 — Distributed storage and file optimization

**Status:** Not started

#### 9.1 Storage systems

- [ ] HDFS basics
- [ ] Object storage and shared access
- [ ] CSV, JSON, Parquet, Avro and ORC
- [ ] Columnar vs row formats
- [ ] Compression and schemas

#### 9.2 Scan optimization

- [ ] Column pruning
- [ ] Predicate pushdown
- [ ] Static and dynamic partition pruning
- [ ] Distinguish storage partitioning from runtime partitions

#### 9.3 Write optimization

- [ ] Read/write modes
- [ ] `partitionBy`
- [ ] Bucketing and its limitations
- [ ] Small files
- [ ] Compaction
- [ ] Schema evolution
- [ ] Output file sizing

**Practical lab**

- [ ] Write identical data as CSV, Parquet and partitioned Parquet; compare scan plans, bytes, file counts and runtime.

**Interview checkpoint**

- [ ] Explain why Parquet helps and diagnose a small-file or partition-pruning problem.

**Completion and evidence**

- [ ] Explain the core mechanisms without notes.
- [ ] Save code, observations and relevant execution plans or metrics.
- [ ] Complete interview checkpoint and revisit weak areas.
- **Date completed:**
- **Evidence / notebook / commit:**
- **Open questions / topics to revisit:**

---

### Week 10 — Delta Lake, Databricks and advanced batch processing

**Status:** Not started

#### 10.1 Lakehouse

- [ ] Data lake vs warehouse vs lakehouse
- [ ] Delta transaction log
- [ ] ACID
- [ ] Time travel
- [ ] Schema enforcement and evolution
- [ ] `MERGE`, `UPDATE` and `DELETE`

#### 10.2 Platform and optimization

- [ ] `OPTIMIZE`
- [ ] `VACUUM` and retention risks
- [ ] Z-order and liquid clustering where supported
- [ ] Databricks compute, jobs and Unity Catalog
- [ ] Distinguish open-source Spark, Delta and platform features

#### 10.3 Batch pipelines

- [ ] Window functions
- [ ] Arrays, maps and structs
- [ ] Nested JSON
- [ ] Deduplication
- [ ] Profiling and validation
- [ ] Incremental loads
- [ ] CDC
- [ ] Bronze/Silver/Gold

**Practical lab**

- [ ] Build an incremental Delta pipeline with deduplication, quality checks and an idempotent merge; document supported runtime features.

**Interview checkpoint**

- [ ] Explain Delta vs Parquet, incremental loading and the role of Databricks.

**Completion and evidence**

- [ ] Explain the core mechanisms without notes.
- [ ] Save code, observations and relevant execution plans or metrics.
- [ ] Complete interview checkpoint and revisit weak areas.
- **Date completed:**
- **Evidence / notebook / commit:**
- **Open questions / topics to revisit:**

---

### Week 11 — Structured Streaming and production pipelines

**Status:** Not started

#### 11.1 Streaming foundations

- [ ] Kafka topics, partitions and offsets
- [ ] Batch vs streaming
- [ ] Micro-batches
- [ ] `readStream` / `writeStream`
- [ ] Triggers and output modes

#### 11.2 Stateful processing

- [ ] Event vs processing time
- [ ] Tumbling, sliding and session windows
- [ ] Watermarking
- [ ] State
- [ ] Late data
- [ ] Checkpoint recovery
- [ ] Source/sink delivery guarantees

#### 11.3 Production foundations

- [ ] Airflow orchestration
- [ ] `spark-submit`
- [ ] Retries and idempotency
- [ ] Logging
- [ ] Data quality
- [ ] Unit and integration tests
- [ ] Monitoring
- [ ] Optional Spark Connect and Pandas API on Spark

**Practical lab**

- [ ] Build a streaming transaction aggregation; inject late events; restart from checkpoint; add tests and a batch orchestration example.

**Interview checkpoint**

- [ ] Explain watermarks, checkpoints and conditions for exactly-once results.

**Completion and evidence**

- [ ] Explain the core mechanisms without notes.
- [ ] Save code, observations and relevant execution plans or metrics.
- [ ] Complete interview checkpoint and revisit weak areas.
- **Date completed:**
- **Evidence / notebook / commit:**
- **Open questions / topics to revisit:**

---

### Week 12 — Production engineering, capstone and interviews

**Status:** Not started

#### 12.1 Production tradeoffs

- [ ] Cluster sizing
- [ ] Cost vs runtime
- [ ] Multi-tenant scheduling
- [ ] Dynamic allocation
- [ ] Remote shuffle services overview
- [ ] Upgrades and compatibility
- [ ] Spark vs Pandas, Polars and DuckDB

#### 12.2 Capstone

- [ ] Integrate batch and streaming paths
- [ ] Validate outputs
- [ ] Document architecture
- [ ] Benchmark baseline vs optimized runs
- [ ] Record failure and recovery experiments
- [ ] Prepare README

#### 12.3 Interview preparation

- [ ] Architecture and execution questions
- [ ] SQL and PySpark coding
- [ ] Join and skew scenarios
- [ ] OOM and slow-job diagnosis
- [ ] Storage and streaming
- [ ] Mock interviews
- [ ] Explain project decisions

**Practical lab**

- [ ] Deliver reproducible project, test suite, execution-plan evidence, benchmark report and mock interview.

**Interview checkpoint**

- [ ] Explain an end-to-end pipeline and defend optimization choices with observed metrics.

**Completion and evidence**

- [ ] Explain the core mechanisms without notes.
- [ ] Save code, observations and relevant execution plans or metrics.
- [ ] Complete interview checkpoint and revisit weak areas.
- **Date completed:**
- **Evidence / notebook / commit:**
- **Open questions / topics to revisit:**

---

## Ongoing capstone — Distributed e-commerce data platform

Start small and scale according to hardware limits. Target datasets are illustrative, not mandatory.

| Dataset | Stretch target |
| :--- | ---: |
| Customers | 1 million |
| Products | 100,000 |
| Orders | 10 million |
| Order items | 50 million |
| Website events | 100 million |
| Categories | 500 |

- [ ] Configurable synthetic data generator with deterministic seed and skew controls.
- [ ] Local and multi-worker cluster execution.
- [ ] Batch ingestion and profiling.
- [ ] Join and shuffle benchmarks.
- [ ] Partitioning, memory and AQE experiments.
- [ ] Parquet and Delta storage.
- [ ] Bronze/Silver/Gold incremental pipeline.
- [ ] Kafka/Structured Streaming pipeline.
- [ ] Tests, orchestration, logging and recovery.
- [ ] Architecture diagram, README and benchmark results.

## Environment plan

- [ ] Local Spark on MacBook (small workloads).
- [ ] Docker standalone cluster with two workers; optionally use idle Windows laptop.
- [ ] Optional real multi-host cluster using compatible runtimes, private networking and shared storage; Azure only within budget.
- [ ] Record Spark, Python, Java and Delta versions and configuration.

## References

- [Apache Spark documentation](https://spark.apache.org/docs/latest/) — use the documentation matching installed version.
- [PySpark API](https://spark.apache.org/docs/latest/api/python/)
- [Spark SQL performance tuning](https://spark.apache.org/docs/latest/sql-performance-tuning.html)
- [Databricks documentation](https://docs.databricks.com/)
- [LeetData Spark in Production](https://leetdata.ai/cohorts/spark-in-production#overview) — supplementary production scenarios.

## Session log

| Date | Week / lesson | Completed | Evidence | Next step |
| :--- | :--- | :--- | :--- | :--- |
| | | | | |

## Interview readiness gate

- [ ] Explain distributed execution from submission to result.
- [ ] Predict stages, partitions and exchanges for a query.
- [ ] Choose and justify physical join strategies.
- [ ] Diagnose skew, shuffle, spill and memory problems from metrics.
- [ ] Write SQL and PySpark solutions independently.
- [ ] Design reliable batch and streaming pipelines.
- [ ] Present capstone and defend tradeoffs.

## Next lesson

Week 1, Lesson 1.1 — Computing fundamentals, followed by manual distributed aggregation.
