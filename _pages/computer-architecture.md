---
layout: page
pagetitle: "Computer Architecture"
permalink: /computer_architecture/
---

The computer architecture notes are mainly from Hennessy and Patterson's book: [Computer Architecture: A Quantitative Approach - 6th edition](https://shop.elsevier.com/books/computer-architecture/hennessy/978-0-12-811905-1), and some online sources. Since the purpose of these notes are for my prelim exam, they will not cover everything in the book - only those which I think might be useful will be included.

## Table of Contents:
- [Chapter 1: Overview](#chapter-1-overview)
  - [§1.1 Processor Performance Trend](#11-processor-performance-trend)
    - [Dennard's Scaling](#dennards-scaling)
    - [Amdahl's Law](#amdahls-law)
    - [Moore's Law](#moores-law)
  - [§1.2 Class of Parallelism and Parallel Architectures](#12-class-of-parallelism-and-parallel-architectures)
- [Memory](#memory)

# Overview
## §1.1 Processor Performance Trend
The growth in processor performance over 40 years: 

<p align="center">
<img src="../assets/images/comp_arch/Growth-in-processor-performance-over-40-years.png" width="95%"/>
</p>

- Prior to mid-1980s growth in processor performance was largely **technology-driven** and averaged about 22% per year.
- After 1986, the increase in growth to about 52% is attributable to **more advanced architecture and organizational ideas typified in RISC architectures**.
- In 2003, **the limits of power due to [Dennard's Scaling](#dennards-scaling) and the available instruction-level parallelism** slowed uniprocessor performance to 23% per year.
- From 2011 to 2015, annual improvement was less than 12%, due to **limits of parallelism of [Amdahl's Law](#amdahls-law)**.
- Since 2015, with **the end of [Moore's Law](#moores-law)**, improvement has been just 3.5% per year.

### Dennard's Scaling
In 1974 Robert Dennard observed that power density was constant for a given area of silicon even as you increased the number of transistors because of smaller dimensions of each transsitor.

Remarkably, transistors could go faster but use less power.

Dennard's Scaling ended around 2004 because current and voltage couldn't keep dropping and still maintain the dependability of integrated circuits. This change forced the microprocessor industry to use **multiple efficient processors** instead of a single inefficient processor. 

Switch from relying solely on instrcution-level parallism (ILP) to data-level parallelism (DLP) and thread-level parallelism (TLP).

### Amdahl's Law
The performance gain that can be obtained by improving some portion of a computer can be calculated using Amdahl's Law. It states that **the performance improvement to be gained from using some faster mode of execution is limited by the fraction of the time the faster mode can be used**.

Amdahl's Law prescribes practical limits to the number of useful cores per chip. If 10% of the task is serial, then the maximum performance benefit from parallelism is 10 no matter how many cores you put on the chip.

### Moore's Law
In 1965 Gordon Moore famously predicted that the number of transistors per chip would double every year, which was amended in 1975 to every two years. That prediction lasted for about 50 years, but no longer holds.

<br/>

The combination of:
- transistors no longer getting much better beacuse of slowing of Moore's Law and the end of Dennard's scaling,
- the unchanging power budgets for microprocessors,
- the replacement of the single power-hungry processor with several energy-efficient processors, and
- the limits to multiprocessoing to achieve Amdahl's Law.

caused improvements in processor performane to slow down.

## §1.2 Class of Parallelism and Parallel Architectures
Parallelism at multiple levels is now the driving force of computer design across all four classes of computers, with **energy** and **cost** being the primary constraints. There are basically two kinds of parallelism in applications:
1. *Data-level parallelism* (DLP) arises because there are many data items that can be operated on at the same time.
2. *Task-level parallelism* (TLP) arises because tasks of work are created that can operate independently and largely in parallel.

Computer hardware in turn can exploit these two kinds of application parallelism in four major ways:

1. 

# Memory Hierarchy Design
The goal is to provide a memory system with a cost per byte that is almost as low as the cheapest level of memory and a speed almost as fast as the fastest level.
  ## §2.1 Basics
  **Locality**:
    - **Spatial locality**: If a particular storage location is referenced at a particular time, then it is likely that nearby memory locations will be referenced in the near future.
    - **Temporal locality**: If at one point a particular memory location is referenced, then it is likely that the same location will be referenced again in the near future.

  The importance of the memory hierarchy has increased with advances in performance of processors. The below figure plots single processor performance projections against the historical performance improvement in time to access main memory. The processor line shows the increase in memory requests per second on average. The memory line shows the incease in memory requests per second on the DRAM.

  <p align="center">
  <img src="../assets/images/comp_arch/processor-memory-gap.png" width="60%"/>
  </p>

  **Concerns**:
  - Memory access time 
      - = Hit time + (Miss rate) x Miss penalty
  - Power consumption 
      - a major consideration more recently
      - caches consumes significant power both as leakage (static) and active (dynamic) power 
      - in PMDs (personal mobile devices) the caches can account for 25% ~ 50% total power consumption
      - trade-off: performance and power consumption

  **Cache placement scheme**: <span style="color: gray;">(To be added more contents later)</span>
  - n-way set associative: n blocks in a set
  - Direct mapp: just one block per set
  - Fully associative: just one set

  **Three categories of cache miss**:
  1. **Compulsory** - the very first access to a block cannot be in the cache.
  2. **Capacity** - if the cache cannot contain all the blocks needed during execution of a program, capacity misses (in addition to compulsory misses) will occur because of blocks being discarded and later retrieved.
  3. **Conflict** - if the block placement strategy is not fully associative, conflict misses (in addition to compulsory and capacity misses) will occur because a block may be discarded and later retrieved if multiple blocks map to its set and accesses to the different blocks are intermingled.

  **To reduce memory access time**:
  - Larger block size to reduce miss rate
    - reduce compulsory misses, slightly reduces static power (lower the numebr of tags)
    - increase miss penalty, increase capacity or conflict misses, especially in smaller caches
  - Bigger caches to reduce miss rate
    - longer hit time
    - higher cost and power (both static and dynamic)
  - Higher associativity to reduce miss rate
    - increase hit time
    - increase power consumption
  - Multilevel caches to reduce miss penalty
    - more power-efficient than single aggregate cache

  ## §2.2 Memory technology and optimizations
  Memory latency is quoted using two measures:
  - Access time: the time between when a read is requested and when the desired word arrives.
  - Cycle time: the minimum time between unrelated requests to memory.

  ### SRAM technology
  




# Pipelining: Basic and Intermediate Concepts
## §3.1 Introduction
What is pipelining?

\- *Pipelining* is an implementation technique whereby multiple instructions are overlapped in execution.



# Instruction Level Parallelism