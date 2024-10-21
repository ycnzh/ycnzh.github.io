---
layout: page
title: Computer Architecture
---

The computer architecture notes are mainly from Hennessy and Patterson's book: [Computer Architecture: A Quantitative Approach - 6th edition](https://shop.elsevier.com/books/computer-architecture/hennessy/978-0-12-811905-1), and some online sources. Since the purpose of these notes are for my prelim exam, they will not cover everything in the book - only those which I think might be useful will be included.

# Computer Architecture 
Source: [Computer Architecture: A Quantitative Approach - 6th edition](https://shop.elsevier.com/books/computer-architecture/hennessy/978-0-12-811905-1)

### Table of Contents:
- [Chapter 1: Overview](#chapter-1-overview)
  - [§1.1 Processor Performance Trend](#11-processor-performance-trend)
    - [Dennard's Scaling](#dennards-scaling)
    - [Amdahl's Law](#amdahls-law)
    - [Moore's Law](#moores-law)
  - [§1.2 Class of Parallelism and Parallel Architectures](#12-class-of-parallelism-and-parallel-architectures)
- [Memory](#memory)

## Chapter 1: Overview
### §1.1 Processor Performance Trend
The growth in processor performance over 40 years: 
![Growth in processor performance over 40 years](./pic/Growth-in-processor-performance-over-40-years.png)

- Prior to mid-1980s growth in processor performance was largely **technology-driven** and averaged about 22% per year.
- After 1986, the increase in growth to about 52% is attributable to **more advanced architecture and organizational ideas typified in RISC architectures**.
- In 2003, **the limits of power due to [Dennard's Scaling](#dennards-scaling) and the available instruction-level parallelism** slowed uniprocessor performance to 23% per year.
- From 2011 to 2015, annual improvement was less than 12%, due to **limits of parallelism of [Amdahl's Law](#amdahls-law)**.
- Since 2015, with **the end of [Moore's Law](h#moores-law)**, improvement has been just 3.5% per year.

#### Dennard's Scaling
In 1974 Robert Dennard observed that power density was constant for a given area of silicon even as you increased the number of transistors because of smaller dimensions of each transsitor.

Remarkably, transistors could go faster but use less power.

Dennard's Scaling ended around 2004 because current and voltage couldn't keep dropping and still maintain the dependability of integrated circuits. This change forced the microprocessor industry to use **multiple efficient processors** instead of a single inefficient processor. 

Switch from relying solely on instrcution-level parallism (ILP) to data-level parallelism (DLP) and thread-level parallelism (TLP).

#### Amdahl's Law
The performance gain that can be obtained by improving some portion of a computer can be calculated using Amdahl's Law. It states that **the performance improvement to be gained from using some faster mode of execution is limited by the fraction of the time the faster mode can be used**.

Amdahl's Law prescribes practical limits to the number of useful cores per chip. If 10% of the task is serial, then the maximum performance benefit from parallelism is 10 no matter how many cores you put on the chip.

#### Moore's Law
In 1965 Gordon Moore famously predicted that the number of transistors per chip would double every year, which was amended in 1975 to every two years. That prediction lasted for about 50 years, but no longer holds.

<br/>

The combination of:
- transistors no longer getting much better beacuse of slowing of Moore's Law and the end of Dennard's scaling,
- the unchanging power budgets for microprocessors,
- the replacement of the single power-hungry processor with several energy-efficient processors, and
- the limits to multiprocessoing to achieve Amdahl's Law.

caused improvements in processor performane to slow down.

### §1.2 Class of Parallelism and Parallel Architectures
Parallelism at multiple levels is now the driving force of computer design across all four classes of computers, with **energy** and **cost** being the primary constraints. There are basically two kinds of parallelism in applications:
1. *Data-level parallelism* (DLP) arises because there are many data items that can be operated on at the same time.
2. *Task-level parallelism* (TLP) arises because tasks of work are created that can operate independently and largely in parallel.

Computer hardware in turn can exploit these two kinds of application parallelism in four major ways:

1. 

## Memory