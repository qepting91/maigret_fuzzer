# Maigret Fuzzer

A Jupyter notebook-based tool for automated username fuzzing and OSINT using [Maigret](https://github.com/soxoj/maigret). The output script then filters by http status code, to help maximize the number of true positives.

## Quick Start

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/19y3JvKQv4bzaZ-A4Td8rLpps8TYl5V0Y?usp=sharing)

Make a copy of my Google Colab notebook to run Maigret Fuzzer directly in your browser without any local setup!

## Prerequisites
- a CSV file containing usernames...such as usernames.csv

## Components

### 1. Username Fuzzer
Generates variations of usernames based on input patterns to expand search coverage.

### 2. Maigret Runner
Executes Maigret searches for each generated username variation, storing results in batch CSV files.

### 3. Results Processor
- Combines all batch results into a master CSV file
- Filters results to show only successful matches (HTTP status 200)
- Creates two output files:
  - `master_results.csv`: All search results
  - `filtered_results.csv`: Only successful matches

  graph TD
    A[usernames.csv] -->|Username Fuzzing| B[fuzzed_usernames.csv]
    B -->|Maigret Search| C[batch_results/*.csv]
    C -->|Combine All Results| D[master_results.csv]
    D -->|Filter HTTP 200| E[filtered_results.csv]

    style A fill:#f9f,stroke:#333
    style B fill:#bbf,stroke:#333
    style C fill:#ddd,stroke:#333
    style D fill:#bfb,stroke:#333
    style E fill:#ff9,stroke:#333


  ## Credits

- [Maigret](https://github.com/soxoj/maigret) - Created by [soxoj](https://github.com/soxoj)

## License

MIT License

Copyright (c) 2024 qepting91

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.