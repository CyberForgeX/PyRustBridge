## PyRustBridge

**PyRustBridge** bridges Python's dynamic and intuitive syntax with Rust's speed and memory safety, enabling developers to supercharge Python applications. This library is perfect for those looking to tackle performance-critical operations without leaving the Python ecosystem, seamlessly integrating Rust's compiled efficiency into Python's interpreted ease.

## Key Features

- **Optimized Performance**: Inject Rust's compiled speed into Python's flexible scripting environment.
- **Simplified Rust-Python Interfacing**: Directly call Rust functions from Python without the usual complexity.
- **Smart Dependency Management**: Automatically resolves and installs dependencies, thanks to an advanced detection system.
- **Robust Environment Handling**: Leverages Minimamba for creating clean, consistent development and deployment environments.
- **Unified Cross-Language Development**: Build and distribute applications that naturally blend Python and Rust code.

## Installation & Setup

Ensure your system is ready with:

- **Rust and Cargo**: Installed via [rustup](https://rustup.rs/). PyRustBridge will check for and install updates as needed.
- **Python 3.8+**: Verify or install from [python.org](https://www.python.org/downloads/) or your system's package manager.
- **Minimamba/Conda**: Install using the [official guide][Micromamba instructions](https://mamba.readthedocs.io/en/latest/installation/micromamba-installation.html).

### Quick Start

Clone and set up **PyRustBridge** with these commands:

```
git clone https://github.com/CyberForgeX/PyRustBridge.git && \
cd PyRustBridge && \
./scripts/setup_environment.py
```

This script prepares your environment, installs dependencies, and ensures **PyRustBridge** is ready for action.

## Utilizing PyRustBridge

To use **PyRustBridge** in your project, simply invoke:

```
prbridge example.py
```

### `example.py` Overview

The provided `example.py` demonstrates **PyRustBridge**'s capability to automate tasks without explicit import statements, showcasing the project's dynamic fix and optimization features:

```python
from datetime import datetime
import logging
import subprocess

log_filename = f"virtualization_setup_{datetime.now().strftime('%Y%m%d%H%M%S')}.log"
logging.basicConfig(filename=log_filename, level=logging.INFO, format='%(asctime)s %(levelname)s: %(message)s', datefmt='%Y-%m-%d %H:%M:%S')

def run_command(command, validate=False, success_msg="", fail_msg="", validation_cmd=""):
    # Command execution and validation logic here
```

This script example highlights **PyRustBridge**'s approach to seamless, efficient Python-Rust integration.

## Contributing to PyRustBridge

Your contributions are welcome! Check our `CONTRIBUTING.md` for guidelines on how to propose changes, report issues, or submit pull requests.

## Acknowledgments

- **The Rust Community**: For developing a system programming language that emphasizes speed and safety.
- **The Python Community**: For creating a versatile language that emphasizes readability and usability.

## License

**PyRustBridge** is made available under the MIT License. For more details, see the `LICENSE` file in the repository.
