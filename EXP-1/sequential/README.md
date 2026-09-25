# Sequential Matrix Multiplication

This folder contains the sequential implementation of matrix multiplication using C.

## Implementation

Matrix multiplication is performed using the traditional sequential approach using three nested loops.

The program multiplies two square matrices and stores the result in a third matrix.

## Contents

- Sequential source code
- Compilation instructions
- Execution output
- Performance results
- Verification result

## Purpose

This implementation serves as the **baseline implementation** for comparing sequential matrix multiplication with parallel implementations such as OpenMP, MPI, and CUDA.

### Matrix Multiplication

```text
Matrix A              Matrix B              Matrix C
┌─────────┐           ┌─────────┐           ┌─────────┐
│ a a a a │           │ b b b b │           │ c c c c │
│ a a a a │     ×     │ b b b b │     =     │ c c c c │
│ a a a a │           │ b b b b │           │ c c c c │
│ a a a a │           │ b b b b │           │ c c c c │
└─────────┘           └─────────┘           └─────────┘

                    C[i][j] =
              Σ A[i][k] × B[k][j]
