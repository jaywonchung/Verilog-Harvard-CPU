# Verilog implementation of CPUs

## Acknowledgements

This is my code and design documents for the SNU Computer Organization (Spring, 2019) course project. This repository only contains the code I wrote myself, thus excluding the TestBench or Memory module. I am opening this repository publicly so as to provide a reference inplementation for various types of CPUs. Please refer to the LICENSE if you want to utilize code from this repository.

## Structure

Generally, features of the CPU stack up as its index increases. For example, `06. Tournament Prediction CPU` also has data-forwarding, which was first introduced in `04. Data Forwarding CPU`.
Each CPU implementation folder contains verilog code and its design document. The design document (`design.pdf`) contains descriptions, logics, and performance analyses of the CPU. 

- `01. Single-cycle CPU`: A single cycle CPU that has an IPC of 1.
- `02. Multi-cycle CPU`: A multi cycle CPU that has an IPC of 1.
- `03. Pipelined CPU`: A 5-stage pipelined CPU. Everything after this has this as its base architecture.
- `04. Data Forwarding CPU`: Data forwarding from the ALU result port to previous pipeline stages.
- `05. 2-Sat Branch Prediction CPU`: Branch prediction with a BTB with 2-bit saturation counter. Previous CPUs always predicted not-taken.
- `06. Tournament Prediction CPU`: The DEC Alpha 21264 tournament branch predictor is implemented (without the line-and-way predictor).
- `07. 2-cycle Memory CPU`: A slightly more realistic CPU that communicates with a slow memory. The variable `LATENCY` (default 2) can be modified to change the latency of the memory.
- `08. Harvard Arch Cached CPU`: An instruction cache and a data cache is implemented. The instruction cache prefetches instructions from the next block to further reduce fetch latency.
- `09. Simple DMA CPU`: A simple DMA module and an its required interrupt mechanism is implemented. 
- `10. Cycle-stealing DMA CPU`: DMA operations are interleaved with instructions that access the data cache to minimize pipeline stall.
