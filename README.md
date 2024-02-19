# PyRustBridge

PyRustBridge offers a seamless integration between Python's dynamic and high-level capabilities and Rust's unparalleled performance and safety. This project is designed for developers looking to enhance their Python applications with the speed of Rust, providing an efficient way to handle performance-critical tasks.

## Features

- **High Performance**: Utilize Rust's performance within your Python applications.
- **Easy Integration**: A straightforward interface between Python and Rust components.
- **Automatic Dependency Management**: Dynamic resolution and installation of dependencies.
- **Environment Management**: Utilize Minimamba for clean, reproducible Python environments.
- **Cross-Language Development**: Develop and distribute applications that leverage both Python and Rust.

## Getting Started

### Prerequisites

- Rust: Install Rust and Cargo using [rustup](https://rustup.rs/).
- Python: Ensure Python 3.8+ is installed on your system.
- Minimamba/Conda: Follow the [Minimamba installation guide](https://github.com/conda-forge/miniforge#mambaforge).

### Installation

Clone the PyRustBridge repository:

```
git clone https://github.com/CyberForgeX/PyRustBridge.git
```
Navigate to the PyRustBridge directory:
```
cd PyRustBridge
```
Execute the setup command:
```
./scripts/setup_environment.sh
```

This command sets up both the Rust and Python environments, installs all necessary dependencies, and prepares the PyRustBridge package for use.
Usage

After installation, you can make a PyRustBridge in your your Python code:

```
prbridge example.py
```
And this

### Example.py script:

# NOTICE HOW THERE ARE NO IMPORTS IN THE SCRIPT BELOW, THAT'S PARTIALLY PyRustBridge FIXES!
```
log_filename = f"virtualization_setup_{datetime.now().strftime('%Y%m%d%H%M%S')}.log"
logging.basicConfig(filename=log_filename, level=logging.INFO, format='%(asctime)s %(levelname)s: %(message)s', datefmt='%Y-%m-%d %H:%M:%S')
def run_command(command, validate=False, success_msg="", fail_msg="", validation_cmd=""):
    try:
        result = subprocess.run(command, check=True, shell=True, stdout=subprocess.PIPE, stderr=subprocess.PIPE, text=True)
        logging.info(f"Success: {success_msg if success_msg else result.stdout}")
        if validate and validation_cmd:
            validation_result = subprocess.run(validation_cmd, shell=True, stdout=subprocess.PIPE, stderr=subprocess.PIPE, text=True)
            if validation_result.stdout.strip() == '1':
                logging.info(f"Validation success for {command}")
            else:
                logging.error(f"Validation failed for {command}")
                print(fail_msg if fail_msg else "Validation failed. Check logs for details.")
        return True
    except subprocess.CalledProcessError as e:
        logging.error(f"Error executing {command}: {e.stderr}")
        print(fail_msg if fail_msg else "An error occurred. Check logs for details.")
        return False
```

### Contributing        
We welcome contributions to PyRustBridge! Please read our contributing guidelines in CONTRIBUTING.md before submitting pull requests.


### License

PyRustBridge is licensed under the MIT License - see the LICENSE file for details.
Acknowledgments

    The Rust Community for providing an excellent system programming language.
    The Python Community for creating a versatile and powerful high-level programming language.


This README provides a concise yet comprehensive overview of the PyRustBridge project, guiding users from installation to usage, contributing, and licensing information. Adjust the repository URL, function names, and any additional project-specific details as necessary.
