# FIFO-vs-LRU
This project is Bash-based simulator that compares two page replacement algorithms used in operating systems:
- FIFO (First-In, First-Out)
- LRU (Least Recently Used)

The project generates random page reference sequences, simulates both algorithms step-by-step, and evaluates their performance using page faults and cache efficiency metrics.

---

##  Table of Contents

- [Features](#features)
- [Algorithms Explained](#algorithms-explained)
- [Requirements](#️requirements)
- [Installation](#installation)
- [Usage](#️usage)
- [Example Output](#example-output)
- [Performance Metrics](#performance-metrics)
- [Project Structure](#project-structure)
- [Experiment Ideas](#experiment-ideas)

---

## Features

- Random page reference sequence generation  
- Step-by-step simulation tables  
- Two algorithms implemented:
  - FIFO
  - LRU  
- Performance analysis:
  - Page faults
  - Hit ratio
  - Miss ratio  
- Automatic file output:
  - Input parameters
  - Full simulation report  
- Input validation for all user inputs  

---

## Algorithms Explained

### FIFO (First-In, First-Out)
- Replaces the **oldest page in memory**
- Uses a queue structure
- Simple but may suffer from **Belady’s anomaly**

### LRU (Least Recently Used)
- Replaces the **least recently used page**
- Tracks usage timestamps
- Typically more efficient than FIFO

---

## Requirements

- Bash (Linux / macOS / WSL on Windows)
- `bc` (optional, for percentage calculations)

Install `bc` if needed:

```bash
sudo apt install bc
```

---

## Installation

Clone the repository

```bash
git clone https://github.com/cybhermes/FIFO-vs-LRU.git
cd FIFO-vs-LRU
```

Make the script executable

```bash
chmod +x FIFOvsLRU.sh
```

---

## Usage

Run the script

```bash
./FIFOvsLRU.sh
```
You will be promted to enter:
- Number of page references
- Maximum page number
- Number of frames (memory size)

---

## Example Output
```bash
=== Porównanie algorytmów FIFO i LRU ===

Wygenerowane odwołania:
1 2 3 2 4 1 5

FIFO Page Replacement:
Reference | Frames | Fault
----------|--------|------
        1 | [1 ]   | 1 
        2 | [1 2 ] | 1
        3 | [1 2 3 ] | 1 
        2 | [1 2 3 ] | 0
```

---

## Performance Metrics 

The simulator calculates:
- Page Faults -> number of misses
- Hits -> successful accesses
- Hit Ratio (%)
- Miss Ratio (%)

### Formulas:

` Hit Ratio = (Hits / Total References) * 100 `

` Miss Ratio = (Page Faults / Total References) * 100 `

---

## Project Structure

├── FIFOvsLRU.sh          # Main simulation script

├── input_parameters.txt  # Saved input data

├── simulation_report.txt # Full results

└── README.md             # Project documentation

---

## Experiment Ideas

Try experimenting with:
- Icreasing number of frames
- Changing reference sequence length
- Comparing behavior for:
    - Small vs Large memory
    - Repeating patterns vs Random input
