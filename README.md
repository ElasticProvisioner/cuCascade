# cuCascade

A GPU memory management and data representation library extracted from the Sirius project.

## Features

- **Memory Management**: GPU, Host, and Disk tier memory allocation and reservation systems
- **Data Representation**: CPU and GPU data representations with batch processing support
- **Topology Discovery**: Hardware topology discovery for optimal memory placement
- **Thread-Safe**: Lock-free memory reservation and data batch management

## Prerequisites

- CUDA 13+
- libcudf 25.10+
- CMake 3.26.4+
- Ninja build system
- C++20 compiler

## Building with Pixi

The project uses [Pixi](https://pixi.sh/) for dependency management:

```bash
# Install pixi if not already installed
curl -fsSL https://pixi.sh/install.sh | bash

# Install dependencies and build
pixi install
pixi run build

# Run tests
pixi run test
```

## Building with CMake

If you prefer to manage dependencies yourself:

```bash
# Configure
cmake --preset release

# Build
cmake --build build/release

# Test
cd build/release && ctest --output-on-failure
```

## Project Structure

```
cuCascade/
├── include/
│   ├── data/           # Data representation headers
│   ├── memory/         # Memory management headers
│   ├── log/            # Logging utilities
│   └── helper/         # Common helper headers
├── src/
│   ├── data/           # Data representation implementation
│   └── memory/         # Memory management implementation
├── test/
│   ├── data/           # Data module tests
│   ├── memory/         # Memory module tests
│   └── utils/          # Test utilities
├── CMakeLists.txt      # Main CMake configuration
├── CMakePresets.json   # CMake presets for build configurations
└── pixi.toml           # Pixi dependency management
```

## Memory Tiers

cuCascade supports three memory tiers:

- **GPU**: Device memory (fastest, limited capacity)
- **HOST**: Pinned host memory (medium speed, larger capacity)
- **DISK**: Storage (slowest, unlimited capacity)

## License

Apache License 2.0
