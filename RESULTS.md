# Assignment 3: Lottery Scheduler Results

## Setup
- **OS**: xv6 (x86)
- **Workload**: A CPU-bound loop implemented in `testlottery.c` that performs mathematical operations in a long loop to keep the CPU busy.
- **Trial**: Three child processes were created with different ticket counts.

## Methodology
1. Child A: 10 tickets
2. Child B: 20 tickets
3. Child C: 30 tickets

Because Child C has 3x the tickets of Child A, it should statistically receive 3x more CPU time.

## Observations
During a 60-second execution:
- Child A finished slowest.
- Child C finished fastest.
- Over a long period, the ratio of CPU time consumed (measured by how many times each process was chosen by the scheduler) converged toward the 1:2:3 ratio defined by the tickets.

## Conclusion
The Lottery Scheduler is probabilistic. Over a short run, variance is high (a process with 1 ticket might win a few times in a row). However, as the run-time increases, the Law of Large Numbers ensures that the actual CPU shares align with the ticket distribution.