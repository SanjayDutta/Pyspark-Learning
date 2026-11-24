# PySpark --- Data Engineering Masterclass

> Living curriculum \| 12 weeks \| 8--10 hours/week \| Junior--intermediate interview target

## How to use this file

-   Mark `[x]` only after explaining the concept independently and completing its relevant exercise.
-   Update the weekly status, evidence and open questions after each lesson.
-   Keep this file in your ChatGPT Project and/or Git repository. Replace the project copy after updates; the downloaded file is not automatically synchronized.
-   Suggested weekly allocation: 3 hours theory, 3--4 hours labs, 1--2 hours review/interview practice, 1 hour documentation.
-   Pace is flexible; do not advance just to meet a calendar deadline.

## Master progress

  ------------------------------------------------------------------------------------------------------
  Week                    Focus                                                  Status
  ----------------------- ------------------------------------------------------ -----------------------
  1                       Distributed computing from first principles            Not started

  2                       Spark architecture and cluster setup                   Not started

  3                       Execution model and fault tolerance                    Not started

  4                       Spark SQL, Catalyst and partitioning                   Not started

  5                       Shuffle and distributed aggregation                    Not started

  6                       Distributed joins and data skew                        Not started

  7                       Memory and resource management                         Not started

  8                       Caching, AQE and performance debugging                 Not started

  9                       Distributed storage and file optimization              Not started

  10                      Delta Lake, Databricks and advanced batch processing   Not started

  11                      Structured Streaming and production pipelines          Not started

  12                      Production engineering, capstone and interviews        Not started
  ------------------------------------------------------------------------------------------------------

## Learning method

For each lesson: understand the problem → understand the mechanism → predict execution → implement → observe metrics → introduce a controlled failure or optimization → answer interview questions.

## Detailed weekly syllabus

### Week 1 --- Distributed computing from first principles

**Status:** Not started

#### 1.1 Computing fundamentals

-   [ ] CPU cores, threads and processes
-   [ ] sequential vs concurrent vs parallel execution
-   [ ] CPU-bound vs I/O-bound workloads
-   [ ] RAM, disk and network bottlenecks

#### 1.2 Distributed systems

-   [ ] Big Data and 3Vs
-   [ ] vertical vs horizontal scaling
-   [ ] partitioning data
-   [ ] data locality
-   [ ] coordination and communication
-   [ ] partial failures and retries

#### 1.3 Manual distributed aggregation

-   [ ] Split transactions across machines
-   [ ] local partial aggregation
-   [ ] combine results
-   [ ] handle repeated keys
-   [ ] reason about network cost
-   [ ] compare Pandas and Spark

**Practical lab**

-   [ ] Implement sequential and multiprocessing aggregation; manually simulate four workers and a failed task.

**Interview checkpoint**

-   [ ] Explain why four machines do not guarantee 4x speedup and when Spark is unnecessary.

**Completion and evidence**

-   [ ] Explain the core mechanisms without notes.

-   [ ] Save code, observations and relevant execution plans or metrics.

-   [ ] Complete interview checkpoint and revisit weak areas.

-   Date completed:

-   Evidence / notebook / commit:

-   Open questions / topics to revisit:

------------------------------------------------------------------------

### Week 2 --- Spark architecture and cluster setup

**Status:** Not started

#### 2.1 Components

-   [ ] Driver
-   [ ] SparkSession and SparkContext
-   [ ] worker nodes
-   [ ] executors
-   [ ] cluster manager
-   [ ] JVM and Python workers
-   [ ] Py4J in classic PySpark

#### 2.2 Deployment

-   [ ] Local mode and local\[N\]
-   [ ] Standalone, YARN and Kubernetes
-   [ ] client vs cluster deploy mode and manager-specific support
-   [ ] spark-submit
-   [ ] application lifecycle

#### 2.3 Cluster laboratory

-   [ ] Install compatible Java and Spark
-   [ ] local Spark UI
-   [ ] Docker master and two workers
-   [ ] executor cores and memory
-   [ ] shared storage
-   [ ] driver and executor connectivity
-   [ ] optional physical or Azure cluster

**Practical lab**

-   [ ] Run the same job locally and on two worker containers; verify executor placement in UI; optionally use separate hosts with private networking and shared storage.

**Interview checkpoint**

-   [ ] Explain worker vs executor vs driver, and how a submitted program reaches multiple machines.

**Completion and evidence**

-   [ ] Explain the core mechanisms without notes.

-   [ ] Save code, observations and relevant execution plans or metrics.

-   [ ] Complete interview checkpoint and revisit weak areas.

-   Date completed:

-   Evidence / notebook / commit:

-   Open questions / topics to revisit:

------------------------------------------------------------------------

### Week 3 --- Execution model and fault tolerance

**Status:** Not started

#### 3.1 Abstractions

-   [ ] RDDs and DataFrames
-   [ ] schemas
-   [ ] transformations vs actions
-   [ ] lazy evaluation
-   [ ] narrow vs wide dependencies

#### 3.2 Scheduling

-   [ ] DAGs
-   [ ] applications, jobs, stages and tasks
-   [ ] stage boundaries
-   [ ] task slots
-   [ ] pipelining
-   [ ] scheduling and retries

#### 3.3 Recovery

-   [ ] RDD lineage
-   [ ] lost partitions
-   [ ] executor loss
-   [ ] task retries
-   [ ] checkpointing introduction
-   [ ] limits of driver recovery

**Practical lab**

-   [ ] Predict stages for filter and aggregation; inspect Jobs and Stages tabs; stop a worker in an isolated lab and observe recovery.

**Interview checkpoint**

-   [ ] Explain how an action triggers execution and why a shuffle creates a stage boundary.

**Completion and evidence**

-   [ ] Explain the core mechanisms without notes.

-   [ ] Save code, observations and relevant execution plans or metrics.

-   [ ] Complete interview checkpoint and revisit weak areas.

-   Date completed:

-   Evidence / notebook / commit:

-   Open questions / topics to revisit:

------------------------------------------------------------------------

### Week 4 --- Spark SQL, Catalyst and partitioning

**Status:** Not started

#### 4.1 SQL engine

-   [ ] DataFrame API vs SQL
-   [ ] temporary and global temporary views
-   [ ] catalogs and tables
-   [ ] analyzed, optimized and physical plans
-   [ ] Catalyst
-   [ ] Tungsten and whole-stage code generation

#### 4.2 Python execution

-   [ ] Built-in expressions vs Python UDFs vs Pandas UDFs
-   [ ] serialization and Arrow
-   [ ] explain extended, formatted and cost

#### 4.3 Partitions

-   [ ] Input, runtime, shuffle and storage partitions
-   [ ] task parallelism
-   [ ] hash and range partitioning
-   [ ] repartition vs coalesce
-   [ ] partition sizing
-   [ ] inspect partition distribution

**Practical lab**

-   [ ] Compare SQL and DataFrame plans; benchmark built-ins vs UDFs; vary partitions and cores; inspect partition counts.

**Interview checkpoint**

-   [ ] Explain how Spark optimizes queries and why adding cores may not improve a stage.

**Completion and evidence**

-   [ ] Explain the core mechanisms without notes.

-   [ ] Save code, observations and relevant execution plans or metrics.

-   [ ] Complete interview checkpoint and revisit weak areas.

-   Date completed:

-   Evidence / notebook / commit:

-   Open questions / topics to revisit:

------------------------------------------------------------------------

### Week 5 --- Shuffle and distributed aggregation

**Status:** Not started

#### 5.1 Shuffle mechanics

-   [ ] Why keys must be colocated
-   [ ] map-side partial aggregation
-   [ ] hash redistribution
-   [ ] shuffle write and read
-   [ ] network transfer
-   [ ] serialization
-   [ ] shuffle files

#### 5.2 Costs and boundaries

-   [ ] Exchange operators
-   [ ] disk I/O
-   [ ] spill vs shuffle
-   [ ] shuffle partition configuration
-   [ ] fetch failures
-   [ ] narrow vs wide operations

#### 5.3 Experiments

-   [ ] filter vs groupBy
-   [ ] distinct
-   [ ] orderBy
-   [ ] repartition
-   [ ] compare shuffle metrics
-   [ ] identify unnecessary exchanges

**Practical lab**

-   [ ] Trace customer aggregation by hand; measure shuffle read/write in Spark UI; compare multiple shuffle partition counts.

**Interview checkpoint**

-   [ ] Explain what moves during a shuffle, why it is expensive and how to reduce it.

**Completion and evidence**

-   [ ] Explain the core mechanisms without notes.

-   [ ] Save code, observations and relevant execution plans or metrics.

-   [ ] Complete interview checkpoint and revisit weak areas.

-   Date completed:

-   Evidence / notebook / commit:

-   Open questions / topics to revisit:

------------------------------------------------------------------------

### Week 6 --- Distributed joins and data skew

**Status:** Not started

#### 6.1 Join semantics

-   [ ] Inner, outer, semi and anti joins
-   [ ] null semantics
-   [ ] duplicate keys and cardinality explosion

#### 6.2 Physical joins

-   [ ] Broadcast hash join
-   [ ] sort-merge join
-   [ ] shuffled hash join
-   [ ] broadcast nested-loop and Cartesian joins
-   [ ] build/probe
-   [ ] join hints
-   [ ] thresholds and statistics

#### 6.3 Skew

-   [ ] Hot keys
-   [ ] uneven partitions
-   [ ] stragglers
-   [ ] salting
-   [ ] pre-aggregation
-   [ ] skew-aware strategies
-   [ ] limitations of repartitioning by the same hot key

**Practical lab**

-   [ ] Join orders and customers using different strategies; verify plans; inject a hot key; measure skew and compare remedies.

**Interview checkpoint**

-   [ ] Choose a join for large-small and large-large tables; diagnose one slow task.

**Completion and evidence**

-   [ ] Explain the core mechanisms without notes.

-   [ ] Save code, observations and relevant execution plans or metrics.

-   [ ] Complete interview checkpoint and revisit weak areas.

-   Date completed:

-   Evidence / notebook / commit:

-   Open questions / topics to revisit:

------------------------------------------------------------------------

### Week 7 --- Memory and resource management

**Status:** Not started

#### 7.1 Memory model

-   [ ] Driver vs executor memory
-   [ ] JVM heap
-   [ ] execution and storage memory
-   [ ] unified memory
-   [ ] off-heap and overhead
-   [ ] Python worker memory

#### 7.2 Failure modes

-   [ ] Garbage collection
-   [ ] disk spill
-   [ ] driver OOM from collect
-   [ ] executor OOM
-   [ ] oversized partitions and broadcasts

#### 7.3 Resource sizing

-   [ ] Executor cores and memory
-   [ ] driver sizing
-   [ ] task concurrency
-   [ ] dynamic allocation
-   [ ] broadcast variables vs broadcast joins
-   [ ] accumulators and retry caveats

**Practical lab**

-   [ ] Inspect memory and GC metrics; safely reproduce bounded memory pressure in a disposable environment; compare configurations.

**Interview checkpoint**

-   [ ] Diagnose driver vs executor OOM and explain why adding memory is not always the answer.

**Completion and evidence**

-   [ ] Explain the core mechanisms without notes.

-   [ ] Save code, observations and relevant execution plans or metrics.

-   [ ] Complete interview checkpoint and revisit weak areas.

-   Date completed:

-   Evidence / notebook / commit:

-   Open questions / topics to revisit:

------------------------------------------------------------------------

### Week 8 --- Caching, AQE and performance debugging

**Status:** Not started

#### 8.1 Reuse

-   [ ] cache and persist
-   [ ] storage levels
-   [ ] lazy materialization
-   [ ] eviction
-   [ ] unpersist
-   [ ] checkpoint vs cache
-   [ ] costs of caching

#### 8.2 AQE

-   [ ] Runtime statistics
-   [ ] shuffle partition coalescing
-   [ ] adaptive join selection
-   [ ] skew join handling
-   [ ] inspect initial and final plans

#### 8.3 Debugging workflow

-   [ ] Spark UI Jobs, Stages, SQL, Executors and Storage
-   [ ] task duration distributions
-   [ ] shuffle, spill, GC and input metrics
-   [ ] event logs and History Server
-   [ ] controlled benchmarking

**Practical lab**

-   [ ] Compare repeated queries with and without caching; compare AQE on/off; diagnose a deliberately slow pipeline using evidence.

**Interview checkpoint**

-   [ ] Explain when caching hurts and how to investigate a slow job systematically.

**Completion and evidence**

-   [ ] Explain the core mechanisms without notes.

-   [ ] Save code, observations and relevant execution plans or metrics.

-   [ ] Complete interview checkpoint and revisit weak areas.

-   Date completed:

-   Evidence / notebook / commit:

-   Open questions / topics to revisit:

------------------------------------------------------------------------

### Week 9 --- Distributed storage and file optimization

**Status:** Not started

#### 9.1 Storage systems

-   [ ] HDFS basics
-   [ ] object storage and shared access
-   [ ] CSV, JSON, Parquet, Avro and ORC
-   [ ] columnar vs row formats
-   [ ] compression and schemas

#### 9.2 Scan optimization

-   [ ] Column pruning
-   [ ] predicate pushdown
-   [ ] static and dynamic partition pruning
-   [ ] distinguish storage partitioning from runtime partitions

#### 9.3 Write optimization

-   [ ] Read/write modes
-   [ ] partitionBy
-   [ ] bucketing and its limitations
-   [ ] small files
-   [ ] compaction
-   [ ] schema evolution
-   [ ] output file sizing

**Practical lab**

-   [ ] Write identical data as CSV, Parquet and partitioned Parquet; compare scan plans, bytes, file counts and runtime.

**Interview checkpoint**

-   [ ] Explain why Parquet helps and diagnose a small-file or partition-pruning problem.

**Completion and evidence**

-   [ ] Explain the core mechanisms without notes.

-   [ ] Save code, observations and relevant execution plans or metrics.

-   [ ] Complete interview checkpoint and revisit weak areas.

-   Date completed:

-   Evidence / notebook / commit:

-   Open questions / topics to revisit:

------------------------------------------------------------------------

### Week 10 --- Delta Lake, Databricks and advanced batch processing

**Status:** Not started

#### 10.1 Lakehouse

-   [ ] Data lake vs warehouse vs lakehouse
-   [ ] Delta transaction log
-   [ ] ACID
-   [ ] time travel
-   [ ] schema enforcement and evolution
-   [ ] MERGE, UPDATE and DELETE

#### 10.2 Platform and optimization

-   [ ] OPTIMIZE
-   [ ] VACUUM and retention risks
-   [ ] Z-order and liquid clustering where supported
-   [ ] Databricks compute, jobs and Unity Catalog
-   [ ] distinguish open-source Spark, Delta and platform features

#### 10.3 Batch pipelines

-   [ ] Window functions
-   [ ] arrays, maps and structs
-   [ ] nested JSON
-   [ ] deduplication
-   [ ] profiling and validation
-   [ ] incremental loads
-   [ ] CDC
-   [ ] Bronze/Silver/Gold

**Practical lab**

-   [ ] Build an incremental Delta pipeline with deduplication, quality checks and an idempotent merge; document supported runtime features.

**Interview checkpoint**

-   [ ] Explain Delta vs Parquet, incremental loading and the role of Databricks.

**Completion and evidence**

-   [ ] Explain the core mechanisms without notes.

-   [ ] Save code, observations and relevant execution plans or metrics.

-   [ ] Complete interview checkpoint and revisit weak areas.

-   Date completed:

-   Evidence / notebook / commit:

-   Open questions / topics to revisit:

------------------------------------------------------------------------

### Week 11 --- Structured Streaming and production pipelines

**Status:** Not started

#### 11.1 Streaming foundations

-   [ ] Kafka topics, partitions and offsets
-   [ ] batch vs streaming
-   [ ] micro-batches
-   [ ] readStream/writeStream
-   [ ] triggers and output modes

#### 11.2 Stateful processing

-   [ ] Event vs processing time
-   [ ] tumbling, sliding and session windows
-   [ ] watermarking
-   [ ] state
-   [ ] late data
-   [ ] checkpoint recovery
-   [ ] source/sink delivery guarantees

#### 11.3 Production foundations

-   [ ] Airflow orchestration
-   [ ] spark-submit
-   [ ] retries and idempotency
-   [ ] logging
-   [ ] data quality
-   [ ] unit and integration tests
-   [ ] monitoring
-   [ ] optional Spark Connect and Pandas API on Spark

**Practical lab**

-   [ ] Build a streaming transaction aggregation; inject late events; restart from checkpoint; add tests and a batch orchestration example.

**Interview checkpoint**

-   [ ] Explain watermarks, checkpoints and conditions for exactly-once results.

**Completion and evidence**

-   [ ] Explain the core mechanisms without notes.

-   [ ] Save code, observations and relevant execution plans or metrics.

-   [ ] Complete interview checkpoint and revisit weak areas.

-   Date completed:

-   Evidence / notebook / commit:

-   Open questions / topics to revisit:

------------------------------------------------------------------------

### Week 12 --- Production engineering, capstone and interviews

**Status:** Not started

#### 12.1 Production tradeoffs

-   [ ] Cluster sizing
-   [ ] cost vs runtime
-   [ ] multi-tenant scheduling
-   [ ] dynamic allocation
-   [ ] remote shuffle services overview
-   [ ] upgrades and compatibility
-   [ ] Spark vs Pandas, Polars and DuckDB

#### 12.2 Capstone

-   [ ] Integrate batch and streaming paths
-   [ ] validate outputs
-   [ ] document architecture
-   [ ] benchmark baseline vs optimized runs
-   [ ] record failure and recovery experiments
-   [ ] prepare README

#### 12.3 Interview preparation

-   [ ] Architecture and execution questions
-   [ ] SQL and PySpark coding
-   [ ] join and skew scenarios
-   [ ] OOM and slow-job diagnosis
-   [ ] storage and streaming
-   [ ] mock interviews
-   [ ] explain project decisions

**Practical lab**

-   [ ] Deliver reproducible project, test suite, execution-plan evidence, benchmark report and mock interview.

**Interview checkpoint**

-   [ ] Explain an end-to-end pipeline and defend optimization choices with observed metrics.

**Completion and evidence**

-   [ ] Explain the core mechanisms without notes.

-   [ ] Save code, observations and relevant execution plans or metrics.

-   [ ] Complete interview checkpoint and revisit weak areas.

-   Date completed:

-   Evidence / notebook / commit:

-   Open questions / topics to revisit:

------------------------------------------------------------------------

## Ongoing capstone --- Distributed e-commerce data platform

Start small and scale according to hardware limits. Target datasets are illustrative, not mandatory.

  Dataset            Stretch target
  ---------------- ----------------
  Customers               1 million
  Products                  100,000
  Orders                 10 million
  Order items            50 million
  Website events        100 million
  Categories                    500

-   [ ] Configurable synthetic data generator with deterministic seed and skew controls.
-   [ ] Local and multi-worker cluster execution.
-   [ ] Batch ingestion and profiling.
-   [ ] Join and shuffle benchmarks.
-   [ ] Partitioning, memory and AQE experiments.
-   [ ] Parquet and Delta storage.
-   [ ] Bronze/Silver/Gold incremental pipeline.
-   [ ] Kafka/Structured Streaming pipeline.
-   [ ] Tests, orchestration, logging and recovery.
-   [ ] Architecture diagram, README and benchmark results.

## Environment plan

-   [ ] Local Spark on MacBook (small workloads).
-   [ ] Docker standalone cluster with two workers; optionally use idle Windows laptop.
-   [ ] Optional real multi-host cluster using compatible runtimes, private networking and shared storage; Azure only within budget.
-   [ ] Record Spark, Python, Java and Delta versions and configuration.

## References

-   [Apache Spark documentation](https://spark.apache.org/docs/latest/) --- use the documentation matching installed version.
-   [PySpark API](https://spark.apache.org/docs/latest/api/python/)
-   [Spark SQL performance tuning](https://spark.apache.org/docs/latest/sql-performance-tuning.html)
-   [Databricks documentation](https://docs.databricks.com/)
-   [LeetData Spark in Production](https://leetdata.ai/cohorts/spark-in-production#overview) --- supplementary production scenarios.

## Session log

  Date   Week / lesson   Completed   Evidence   Next step
  ------ --------------- ----------- ---------- -----------
                                                

## Interview readiness gate

-   [ ] Explain distributed execution from submission to result.
-   [ ] Predict stages, partitions and exchanges for a query.
-   [ ] Choose and justify physical join strategies.
-   [ ] Diagnose skew, shuffle, spill and memory problems from metrics.
-   [ ] Write SQL and PySpark solutions independently.
-   [ ] Design reliable batch and streaming pipelines.
-   [ ] Present capstone and defend tradeoffs.

## Next lesson

Week 1, Lesson 1.1 --- Computing fundamentals, followed by manual distributed aggregation.
