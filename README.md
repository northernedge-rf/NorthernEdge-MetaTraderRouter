# Northern Edge Robotics & Fabrication: MetaTrader High-Frequency Router Daemon

[![C++ Standard](https://img.shields.io/badge/C%2B%2B-17-blue.svg)](https://en.wikipedia.org/wiki/C%2B%2B17)
[![Build Status](https://img.shields.io/badge/Build-Passing-success.svg)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

An ultra-low latency, concurrent asynchronous broker access server latency routing engine developed by **Northern Edge Robotics & Fabrication**. Engineered for high-frequency trading (HFT) and precision robotic control loops requiring sub-millisecond execution precision.

---

## Architecture & Performance

- **Asynchronous Concurrent Polling**: Utilizes `std::async` and futures to query multiple broker access socket arrays in parallel, eliminating sequential network bottle-necking.
- **High-Resolution Timing**: Measures round-trip execution times using `std::chrono::high_resolution_clock` with microsecond-level accuracy.
- **Dynamic Failover & Routing**: Automatically sorts and locks onto the lowest-latency endpoint in real-time, ensuring zero-downtime stream continuity for MetaTrader and robotic control backends.

---

## Building and Execution

### Prerequisites
- Modern C++17 compliant compiler (GCC 9+, Clang 10+, or MSVC 2019+)
- CMake 3.15 or higher

### Compilation Steps
```bash
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
cmake --build .
```

### Running the Daemon
```bash
./mt_router
```

---

## License
Distributed under the MIT License. See `LICENSE` for more information.
