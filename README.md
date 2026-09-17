# IndexIT

IndexIT is a Windows-focused local document search engine written in C/C++. The project is designed to index files on a machine, tokenize and rank their content, and support fast local queries without depending on cloud services or heavyweight indexing infrastructure.

This repository is intended to be a practical and efficient search solution for local document collections, with a focus on:

- native Windows file discovery and scanning
- fast in-memory term lookup using trie and hash table structures
- inverted index storage for document-term mapping
- TF-IDF / BM25-style ranking for relevant results
- cache-aware storage to avoid uncontrolled memory growth
- a lightweight CLI interface for indexing and searching

Repository: https://github.com/Normandy9/IndexIT.git

---

## Features

- Local document indexing for Windows directories
- Fast search over indexed content
- Efficient term lookup using trie and hash-based structures
- Ranking of search results by relevance
- Disk-aware cache management
- Modular C project design for easy extension

---

## Project Structure

```text
IndexIT/
├── include/                 # Public headers and module contracts
├── src/                     # Main source code
│   ├── core/
│   ├── index/
│   ├── cache/
│   ├── db/
│   ├── query/
│   ├── benchmark/
│   └── main.c
├── tests/                   # Test cases for core modules
├── data/                    # Sample input datasets
├── benchmarks/              # Benchmark outputs and logs
├── docs/                    # Documentation and planning notes
├── third_party/              # Vendored dependencies
├── .gitignore
├── CMakeLists.txt
├── README.md
└── LICENSE
```

---

## Prerequisites

- Windows 10 or Windows 11
- CMake 3.20+
- MSVC or MinGW-w64
- Git
- Optional: SQLite, miniz, or document parsing libraries as the project expands

---

## Build

```bash
mkdir build
cd build
cmake ..
cmake --build .
```

---

## Usage

```bash
indexit.exe index <folder_path>
indexit.exe search "<query>"
indexit.exe stats
indexit.exe clean
```

---

## Development Notes

This project follows a modular architecture designed to separate concerns between:

- file discovery and extraction
- tokenization and indexing
- ranking and query execution
- persistence and caching
- benchmarking and testing

The goal is to create a local search engine that is lightweight, fast, and transparent enough to understand and extend.

---

## License

This project is open for learning and development use. Please review the repository license before production or commercial use.

---

## Contributing

Contributions, suggestions, and improvements are welcome. You can fork the repository and open a pull request with your changes.
