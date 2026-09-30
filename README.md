# MPI Token Ring

A distributed-systems lab project written in C using the Message Passing Interface (MPI). It demonstrates token-based mutual exclusion by coordinating access to a simulated shared printer across multiple processes.

## Overview

The program creates a logical ring of exactly three MPI processes. A single token circulates from one process to the next, allowing only the process holding the token to enter the critical section and use the shared printer.

## How It Works

1. Process 0 starts with the token.
2. The token holder accesses and releases the simulated printer.
3. The token is sent to the next process in the ring.
4. After all processes have received it, the token returns to Process 0.

## Concepts Demonstrated

- Distributed processes with MPI
- Point-to-point communication using `MPI_Send` and `MPI_Recv`
- Token-ring topology
- Mutual exclusion and critical-section coordination
- Process ranks and inter-process synchronization

## Requirements

- A C compiler
- An MPI implementation such as Open MPI or Microsoft MPI

## Build

```bash
mpicc token_ring.c -o token_ring
```

## Run

The current implementation requires exactly three processes:

```bash
mpiexec -n 3 ./token_ring
```

On Windows, run the generated executable as follows:

```bash
mpiexec -n 3 token_ring.exe
```

## Project Structure

- `token_ring.c` — Implements the token-ring simulation and shared-printer coordination.
