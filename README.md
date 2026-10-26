<div align="center">

```mermaid
mindmap
    root((Parallel Computation))
        Foundations
            Concurrency
            Parallelism
            Dependencies
            Critical path
            Granularity
                Fine-grained
                Coarse-grained
                Embarrassingly parallel
            Performance laws
                Amdahl law
                Gustafson law
                Strong scaling
                Weak scaling

        Parallelism Types
            Bit-level
            Instruction-level
                Pipelining
                Superscalar execution
                Out-of-order execution
            Data parallelism
                SIMD
                Vectorization
                GPU kernels
            Task parallelism
                Independent tasks
                Task graphs
                Pipelines
            Request parallelism
                Servers
                Work queues

        Flynn Taxonomy
            SISD
            SIMD
            MISD
            MIMD
                SPMD
                MPMD

        Memory Models
            Shared memory
                UMA
                NUMA
                Cache coherence
            Distributed memory
                Local address spaces
                Message passing
            Hybrid memory
                Cluster of multicore nodes
                CPU and GPU memory

        Architectures
            Multicore CPU
            Symmetric multiprocessing
            NUMA server
            GPU
            Vector processor
            Cluster
            Supercomputer
            Cloud HPC
            FPGA

        Programming Models
            Threads
            OpenMP
            MPI
            CUDA
            OpenACC
            SYCL
            C plus plus parallel algorithms
            Task runtimes

        Synchronization
            Mutex
            Semaphore
            Barrier
            Atomic operation
            Reduction
            Lock-free structures
            Memory ordering

        Toolkit
            Compilers
                GCC
                Clang LLVM
                Intel compilers
                NVIDIA HPC SDK
            CPU tools
                OpenMP runtime
                Thread sanitizer
                perf
                VTune
            Distributed tools
                Open MPI
                MPICH
                Slurm
                InfiniBand
            GPU tools
                CUDA Toolkit
                Nsight Systems
                Nsight Compute
                ROCm
            Libraries
                BLAS
                LAPACK
                oneMKL
                cuBLAS
                cuFFT
                Thrust
            Profiling
                Timing
                Hardware counters
                Tracing
                Roofline analysis

        Correctness Risks
            Race condition
            Deadlock
            Livelock
            False sharing
            Data dependency
            Nondeterminism
            Numerical reproducibility

        Performance Risks
            Serial fraction
            Communication overhead
            Synchronization overhead
            Load imbalance
            Memory bandwidth
            Cache misses
            Network latency
            Kernel launch overhead
```

# **`Awesome`** [Parallel Computation](https://wikipedia.org/wiki/Parallel_computing) [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
</div>

[![YouTube](https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white)]()
[![Reddit](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge&logo=reddit&logoColor=white)](https://www.reddit.com/r/HPC/new/)

<p align="center">
    <a href="https://github.com/cybersecurity-dev/"><img height="25" src="https://github.com/cybersecurity-dev/cybersecurity-dev/blob/main/assets/github.svg" alt="GitHub"></a>
    &nbsp;
    <a href="https://www.youtube.com/@CyberThreatDefense"><img height="25" src="https://github.com/cybersecurity-dev/cybersecurity-dev/blob/main/assets/youtube.svg" alt="YouTube"></a>
    &nbsp;
    <a href="https://cyberthreatdefence.com/my_awesome_lists"><img height="20" src="https://github.com/cybersecurity-dev/cybersecurity-dev/blob/main/assets/blog.svg" alt="My Awesome Lists"></a>
    <img src="https://github.com/cybersecurity-dev/cybersecurity-dev/blob/main/assets/bar.gif">
</p>

```mermaid
flowchart TD
    START(["Python program is too slow or unresponsive"])

    START --> PROFILE["Measure and profile"]
    PROFILE --> TYPE{"Workload type?"}

    TYPE -->|"Mostly waiting"| IO["I/O-bound"]
    TYPE -->|"Mostly calculating"| CPU["CPU-bound"]
    TYPE -->|"Waiting and calculating"| MIXED["Mixed pipeline"]

    IO --> AMOUNT{"Concurrency size?"}
    AMOUNT -->|"Moderate"| THREAD["Threads"]
    AMOUNT -->|"Large"| ASYNC["asyncio"]
    AMOUNT -->|"Simple worker pool"| TPOOL["ThreadPoolExecutor"]

    CPU --> CPUCHOICE{"Execution strategy?"}
    CPUCHOICE -->|"Multiple CPU cores"| PROCESS["Multiprocessing"]
    CPUCHOICE -->|"Simple worker pool"| PPOOL["ProcessPoolExecutor"]
    CPUCHOICE -->|"Array computation"| NUMPY["NumPy or native library"]
    CPUCHOICE -->|"Massive data parallelism"| GPU["GPU"]

    MIXED --> PIPE["asyncio plus process pool"]

    THREAD --> CHECK
    ASYNC --> CHECK
    TPOOL --> CHECK
    PROCESS --> CHECK
    PPOOL --> CHECK
    NUMPY --> CHECK
    GPU --> CHECK
    PIPE --> CHECK

    CHECK{"Shared mutable data?"}

    CHECK -->|"Yes"| SYNC["Lock, Queue, Pipe,<br/>shared memory or isolation"]
    CHECK -->|"No"| BENCH["Benchmark"]

    SYNC --> BENCH
    BENCH --> RESULT{"Faster and correct?"}

    RESULT -->|"No"| PROFILE
    RESULT -->|"Yes"| END(["Use selected model"])

    classDef terminal fill:#306998,color:#fff,stroke:#1f4768,stroke-width:3px
    classDef decision fill:#ffd43b,color:#111,stroke:#b7950b,stroke-width:2px
    classDef io fill:#e3f2fd,color:#111,stroke:#1e88e5
    classDef cpu fill:#e8f5e9,color:#111,stroke:#43a047
    classDef mixed fill:#f3e5f5,color:#111,stroke:#8e24aa
    classDef safety fill:#ffebee,color:#111,stroke:#e53935

    class START,END terminal
    class TYPE,AMOUNT,CPUCHOICE,CHECK,RESULT decision
    class IO,THREAD,ASYNC,TPOOL io
    class CPU,PROCESS,PPOOL,NUMPY,GPU cpu
    class MIXED,PIPE mixed
    class SYNC,BENCH,PROFILE safety
```

## 📖 Contents
- [My Awesome Lists](#my-awesome-lists)
- [Contributing](#contributing)
- [Contributors](#contributors)

---
---

### Parallelism vs Concurrency


##

### My Awesome Lists
You can access the my awesome lists [here](https://cyberthreatdefence.com/my_awesome_lists)

### Contributing

[Contributions of any kind welcome, just follow the guidelines](contributing.md)!

### Contributors

[Thanks goes to these contributors](https://github.com/cybersecurity-dev/awesome-parallel-computation/graphs/contributors)!

[🔼 Back to top](#awesome-parallel-computation-)
