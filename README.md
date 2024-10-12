# Cache Simulation Project

This project simulates the behavior of a CPU cache memory system using various configurations and parameters such as cache size, block size, and associativity. The cache follows the **Least Recently Used (LRU)** replacement policy and processes read requests to check for cache hits and misses.

The simulation runs on multiple trace files containing memory access addresses, and it measures the hit rate, miss rate, and overall performance of the cache for different configurations. Additionally, the project visualizes the effect of changing these parameters on cache performance through plots.

---

## Features

- **Configurable Cache System**: The simulation allows you to specify different cache sizes, block sizes, and associativity levels.
- **Support for Multiple Trace Files**: The project simulates cache behavior for several trace files, each representing different program workloads (e.g., gcc, gzip, swim, etc.).
- **Hit/Miss Tracking**: The simulation tracks and displays cache hit and miss counts for each trace file.
- **LRU Replacement Policy**: The cache implements an LRU replacement strategy to evict the least recently used cache blocks.
- **Performance Comparison**: The project compares cache performance metrics such as hit rate and miss rate across various configurations of cache size, block size, and associativity.
- **Visualization**: Graphs are generated to visually compare cache performance metrics as cache parameters are varied.

---

## Cache Structure

The project simulates a cache system composed of:
- **Cache Blocks**: Each cache block holds a portion of the data from memory, along with its tag, validity, and LRU information.
- **Sets**: The cache is divided into sets, and each set contains multiple cache blocks.
- **Associativity**: Each set can hold multiple blocks based on the associativity (direct-mapped, fully associative, or set associative).

---

## Simulation Overview

### 1. Cache Configuration

The cache is configured using three main parameters:
- **Cache Size**: The total size of the cache in bytes (e.g., 64KB, 128KB, etc.).
- **Block Size**: The size of each cache block in bytes (e.g., 4B, 8B, 16B, etc.).
- **Associativity**: Defines how many blocks can be stored in each cache set (e.g., direct-mapped (1-way), 2-way, 4-way, fully associative).

### 2. Replacement Policy

The cache implements an **LRU (Least Recently Used)** replacement policy, which means that when a cache miss occurs and the cache set is full, the least recently accessed block is evicted to make room for the new data.

### 3. Memory Access Simulation

The simulation reads memory addresses from the trace files, converts them from hexadecimal to binary, and processes them through the cache:
- **Cache Hit**: If the requested address is already present in the cache, it's a cache hit, and the LRU counters are updated.
- **Cache Miss**: If the address is not found, it's a cache miss, and the cache needs to load the data into one of the cache blocks, potentially evicting an existing block.

### 4. Trace Files

The simulation runs on five trace files:
- `gcc.trace`
- `gzip.trace`
- `mcf.trace`
- `swim.trace`
- `twolf.trace`

Each trace file contains a series of memory addresses that simulate real program workloads.

---

## Parts of the Project

The project is divided into several parts, each performing a different analysis of cache performance:

### **Part A**: Fixed Cache Configuration
In this part, the cache size, block size, and associativity are fixed, and the simulation processes each trace file, calculating and displaying the hit rate and miss rate.

### **Part B**: Varying Cache Size
In Part B, the cache size is varied (from 128KB to 2MB), while the block size and associativity are fixed. The simulation tracks how cache size affects hit rate and miss rate, and the results are visualized through plots.

### **Part C**: Varying Block Size
Part C varies the block size (from 1B to 128B) while keeping the cache size and associativity constant. The simulation measures the impact of block size on cache performance and visualizes the results.

### **Part D**: Varying Associativity
In Part D, the associativity is varied (from direct-mapped to fully associative), with the cache size and block size remaining constant. This part explores how increasing associativity affects hit rate and miss rate, with the results presented in both tabular and graphical form.


## How to Run the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/Subhashhari/Cache_simulator.git
   cd cache-simulation
