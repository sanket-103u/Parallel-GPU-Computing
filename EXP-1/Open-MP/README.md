# OpenMP Matrix Multiplication

This folder contains the parallel implementation of matrix multiplication using **OpenMP** in C.

The program uses multiple CPU threads to perform matrix multiplication simultaneously. This implementation is developed as a parallel version of the sequential matrix multiplication program.

---

## Objective

The objectives of this experiment are:

- To implement matrix multiplication using OpenMP.
- To perform matrix multiplication using multiple CPU threads.
- To reduce the execution time compared with sequential execution.
- To understand parallel execution using OpenMP.
- To measure the execution time of the parallel implementation.
- To verify the correctness of the calculated matrix.

---

## OpenMP

OpenMP stands for **Open Multi-Processing**.

It is an API used for parallel programming on shared-memory systems.

OpenMP allows a program to divide computational work among multiple CPU threads.

In this experiment, the matrix multiplication operation is divided among multiple threads so that different parts of the matrix can be calculated simultaneously.

---

## Working Principle

Matrix multiplication involves calculating every element of the result matrix `C`.

The basic operation is:

```text
C[i][j] = Σ A[i][k] × B[k][j]

                 CPU
                  │
        ┌─────────┼─────────┐
        │         │         │
        ▼         ▼         ▼
    Thread 1   Thread 2   Thread 3
        │         │         │
        ▼         ▼         ▼
       ...       ...       ...
        │         │         │
        ▼         ▼         ▼
    Thread 30  Thread 31  Thread 32
        │         │         │
        └─────────┼─────────┘
                  ▼
             Matrix C

Start
  │
  ▼
Initialize Matrix A and B
  │
  ▼
Initialize Matrix C
  │
  ▼
Start Execution Timer
  │
  ▼
Create OpenMP Threads
  │
  ▼
Divide Matrix Computation
  │
  ├──────────────┬──────────────┐
  ▼              ▼              ▼
Thread 1      Thread 2       Thread N
  │              │              │
  ▼              ▼              ▼
Calculate      Calculate      Calculate
part of C      part of C      part of C
  │              │              │
  └──────────────┴──────────────┘
                 │
                 ▼
          Complete Matrix C
                 │
                 ▼
        Stop Execution Timer
                 │
                 ▼
         Verify Matrix Result
                 │
                 ▼
        Display Execution Time
                 │
                 ▼
                End
