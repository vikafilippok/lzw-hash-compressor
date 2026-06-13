# LZW Hash Compressor

File compression and decompression tool based on the LZW algorithm, implemented in C with hash table optimization.

## About

This project implements LZW compression and decompression for binary files.
The encoder uses a hash table to speed up dictionary lookup during compression. The program supports configurable dictionary sizes and works with input and output files through command-line arguments.

## Features

* Compresses files using the LZW algorithm
* Decompresses files back to their original form
* Uses a hash table for faster dictionary lookup
* Supports configurable dictionary size from 12 to 28 bits
* Works with binary files
* Uses buffered bit-level input/output
* Prints compression statistics and execution time

## Project Structure

```text
.
├── CMakeLists.txt
├── main.c
├── gtbitio.c
├── gtbitio.h
├── utypes.h
└── .gitignore
```

## Build

```bash
mkdir build
cd build
cmake ..
cmake --build .
```

## Usage

### Compress a file

```bash
./lzw_hash -c input.txt compressed.lzw
```

### Compress with custom dictionary size

```bash
./lzw_hash -c16 input.txt compressed.lzw
```

`N` can be from `12` to `28`.

### Decompress a file

```bash
./lzw_hash -d compressed.lzw output.txt
```

## Example

```bash
./lzw_hash -c16 example.txt example.lzw
./lzw_hash -d example.lzw restored.txt
```

After decompression, `restored.txt` should contain the same data as the original input file.

## Educational Purpose

This repository was created as an educational project for studying data compression algorithms, dictionary-based encoding, hash tables, and bit-level file I/O in C.
