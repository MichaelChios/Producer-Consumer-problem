# Producer-Consumer Problem (C)

This repository contains a simple implementation of the classic Producer–Consumer problem written in C.

Producer–Consumer Problem: multiple producer threads generate data and place it into a bounded buffer while multiple consumer threads remove and process data from that buffer. The implementation demonstrates thread synchronization using mutexes and semaphores (or equivalent synchronization primitives).

Files
- `producer_consumer.c` — main C source implementing the bounded buffer, producers, and consumers.
- `README.md` — this file.

Features
- Single-file, self-contained example suitable for learning and experimentation.
- Demonstrates thread synchronization (mutexes/semaphores) and a bounded buffer.

Requirements
- A C compiler with POSIX threads support (GCC/Clang). For best results build and run on Linux or WSL.
- On native Windows, use WSL or install MinGW-w64 and a pthreads implementation if you need a native build.

Build & Run

On Linux or WSL:

```bash
gcc -o producer_consumer producer_consumer.c -pthread
./producer_consumer
```

On Windows with MinGW-w64 (when pthreads is available):

```powershell
gcc -o producer_consumer.exe producer_consumer.c -lpthread
.\producer_consumer.exe
```

If compilation fails due to missing pthreads on native Windows, run the program inside WSL or a Linux environment.

Usage
- Run the compiled binary. The program prints status messages indicating producers adding items and consumers removing items.
- If the program accepts command-line arguments (e.g., buffer size, number of producers/consumers), check the top of `producer_consumer.c` for details.

Testing ideas
- Vary the number of producers/consumers and buffer capacity to observe synchronization behavior.
- Add logging or timestamps to measure throughput and latency.

Notes
- This example is intended for education and demonstration rather than production use.
- For a native Windows port, replace POSIX synchronization with Win32 primitives or use a cross-platform abstraction.