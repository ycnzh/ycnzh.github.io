The computer architecture notes are mainly from Hennessy and Patterson's book: [Computer Architecture: A Quantitative Approach - 6th edition](https://shop.elsevier.com/books/computer-architecture/hennessy/978-0-12-811905-1), and some online sources. Since the purpose of these notes are for my prelim exam, they will not cover everything in the book - only which I think might be useful will be included.

# Computer Architecture 
Source: [Computer Architecture: A Quantitative Approach - 6th edition](https://shop.elsevier.com/books/computer-architecture/hennessy/978-0-12-811905-1)

## Overview
The growth in processor performance over 40 years: 
![Growth in processor performance over 40 years](./pic/Growth-in-processor-performance-over-40-years.png)

- Prior to mid-1980s growth in processor performance was largely **technology-driven** and averaged about 22% per year.
- After 1986, the increase in growth to about 52% is attributable to **more advanced architecture and organizational ideas typified in RISC architectures**.
- In 2003, **the limits of power due to Dennard's Scaling and the available instruction-level parallelism** slowed uniprocessor performance to 23% per year.
- From 2011 to 2015, annual improvement was less than 12%, due to **limits of parallelism of Amdahl's Law**.
- Since 2015, with **the end of Moore's Law**, improvement has been just 3.5% per year.
## Memory