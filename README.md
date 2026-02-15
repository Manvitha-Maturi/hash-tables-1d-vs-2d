# Hash Tables: 1D Linear Probing vs 2D Bucketed Table (C++)

This project compares two hash table designs by measuring how many “spots” (slots checked) are needed during:
- insertion
- selective removal
- second insertion
- search

The program generates **100 unique random integers (1–1000)**, performs operations on both structures, and prints the total number of spots checked for each phase.

---

## What’s included

### 1) 1D Hash Table (Linear Probing)
- Fixed size array of **500** slots
- Hash: `h(x) = x % 500`
- Collision handling: **linear probing**
- Removal reinserts subsequent clustered items to keep probing valid

Files:
- `PartA.h`
- `PartA.cpp`

### 2) 2D Hash Table (Row Buckets)
- **100 rows**, each row has **5 slots**
- Hash: `h(x) = x % 100` → selects a row
- Collisions handled by placing values into the next available slot **within the same row**
- Removal shifts remaining row items left to keep row compact

Files:
- `PartB.h`
- `PartB.cpp`

### Driver / Experiment
- Generates the dataset
- Inserts first 50 values
- Removes values among the first 50 where `x % 7 == 0`
- Inserts remaining 50 values
- Searches values where `x % 9 == 0`

File:
- `main.cpp`

---

## How to build and run

### Build with g++ (Mac/Linux/WSL)
From the project folder:
```bash
g++ -std=c++17 -O2 main.cpp PartA.cpp PartB.cpp -o hash_compare
./hash_compare
