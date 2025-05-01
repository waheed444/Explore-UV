# 📌 Introduction to UV

**UV** is a cutting-edge Python packaging and dependency management tool that has been designed to replace **pip**. UV offers a more efficient, modern approach to managing Python packages, providing enhanced performance and better handling of dependencies. With UV, developers can streamline their workflows, optimize package installations, and ensure cleaner and more reliable environments.

## Table of Contents

1. Why Use `uv`?
2. Prerequisites
3. Installing `uv`
4. Core `uv` Commands and Use Cases
   - Virtual Environment Management
   - Package Management
   - Project Management
   - Python Version Management
   - Script and Tool Management
   - Advanced Features
5. Migrating from `pip`
6. Additional Resources

### Key Enhancements Over Pip

- **Speed**: UV is optimized for faster package installation and resolution, reducing the time spent on setting up environments and installing dependencies.
- **Improved Dependency Resolution**: UV uses a more sophisticated algorithm to resolve dependencies, minimizing the chance of version conflicts and ensuring a smoother installation process.
- **Built-in Virtual Environment Management**: Unlike pip, which requires external tools like `virtualenv`, UV offers built-in support for creating and managing virtual environments.
- **Automatic Compatibility Checks**: UV ensures that your Python version is compatible with the installed packages and dependencies, minimizing compatibility issues.
- **Streamlined User Interface**: UV features a simplified command structure that makes it easier to manage Python environments and packages directly from the command line.

### Why Switch to UV?
- **Speed**: 10-100x faster than `pip` for package installation and dependency resolution, thanks to its Rust implementation.
- **Unified Tool**: Replaces multiple tools (`pip`, `virtualenv`, `poetry`, `pipx`, `pyenv`) with a single binary.
- **Compatibility**: Works with existing `requirements.txt` files and Python packaging standards.
- **Simplified Workflow**: Combines virtual environment creation, package management, and project setup in one tool.
- **Cross-Platform**: Supports Linux, Windows, and macOS.

## Prerequisites

- **Python**: Ensure Python (version 3.7 or higher) is installed on your system, as `uv` requires a Python interpreter to manage dependencies and build packages.
- **Internet Connection**: Required for downloading `uv`, Python versions, and packages from PyPI.


## Highlights

- 🚀 A single tool to replace `pip`, `pip-tools`, `pipx`, `poetry`, `pyenv`, `twine`, `virtualenv`,
  and more.
- ⚡️ 10-100x faster than `pip`.
- 🗂️ Provides [comprehensive project management](#projects), with a
  [universal lockfile](https://docs.astral.sh/uv/concepts/projects/layout#the-lockfile).
- ❇️ [Runs scripts](#scripts), with support for
  [inline dependency metadata](https://docs.astral.sh/uv/guides/scripts#declaring-script-dependencies).
- 🐍 [Installs and manages](#python-versions) Python versions.
- 🛠️ [Runs and installs](#tools) tools published as Python packages.
- 🔩 Includes a [pip-compatible interface](#the-pip-interface) for a performance boost with a
  familiar CLI.
- 🏢 Supports Cargo-style workspaces for
  scalable projects.
- 💾 Disk-space efficient, with a global cache for
  dependency deduplication.
- ⏬ Installable without Rust or Python via `curl` or `pip`.
- 🖥️ Supports macOS, Linux, and Windows.

## Installing `uv`

### Option 3: Using `pip` (Temporary, for Migration)

If you need to install `uv` in a Python environment:

```bash
pip install uv
```

Verify installation:

```bash
uv --version
```

**Use Case**: Install `uv` to start managing Python projects and packages without relying on `pip` or other tools.

## Core `uv` Commands and Use Cases

Below are all essential `uv` commands, grouped by functionality, with their use cases and examples.

### Create Project Manager

```bash
uv init <project-name>
```
The `uv init` command, part of the uv Python package manager, initializes a new `Python project` by creating a directory with a `pyproject.toml` file for metadata and dependencies, and optionally a virtual environment.

```
project-name/
├── pyproject.toml
└── src/
    └── project_name/
        └── __init__.py
        └── __readme.md
```

### Virtual Environment Management

`uv` simplifies creating and managing virtual environments, which are isolated Python environments for project-specific dependencies.

#### Create a Virtual Environment

```bash
uv venv
```

- **Use Case**: Creates a virtual environment in the `.venv` directory in your current project folder. Use this to isolate project dependencies.
- **Example**: `uv venv` creates `.venv` with the system's default Python version.
- **Note**: If the required Python version is unavailable, `uv` can download it automatically (see Python Version Management).

#### Create a Virtual Environment with a Specific Python Version

```bash
uv venv --python 3.11
```

- **Use Case**: Creates a virtual environment using a specific Python version (e.g., 3.11). Useful when a project requires a particular Python version.
- **Example**: `uv venv --python 3.11` creates `.venv` with Python 3.11.

#### Activate a Virtual Environment

```bash
# On Linux/macOS (bash/zsh)
source .venv/bin/activate

# On Windows (Command Prompt)
.venv\Scripts\activate

# On Windows (PowerShell)
.\.venv\Scripts\Activate.ps1
```

- **Use Case**: Activates the virtual environment, making its Python interpreter and packages available in your shell.
- **Example**: After activation, running `python --version` shows the virtual environment’s Python version.

### Package Management

`uv` provides commands to install, remove, and manage packages, replacing `pip` entirely.

#### Install a Package

```bash
uv add <package>
```

- **Use Case**: Installs a package into the active virtual environment. Use this to add dependencies like `requests` or `numpy`.
- **Example**: `uv pip install requests` installs the `requests` library.
- **Note**: Requires an active virtual environment unless using `--system` (see Advanced Features).

#### Install Multiple Packages

```bash
uv add <package1> <package2>
```

- **Use Case**: Installs multiple packages at once.
- **Example**: `uv pip install flask django` installs both `flask` and `django`.

#### Install from a `requirements.txt` File

```bash
uv add -r requirements.txt
```

- **Use Case**: Installs all packages listed in a `requirements.txt` file. Ideal for replicating project dependencies.
- **Example**: `uv pip install -r requirements.txt` installs all dependencies from the file.
- **Note**: `uv` is fully compatible with `pip`-generated `requirements.txt` files.

#### Uninstall a Package

```bash
uv remove <package>
```

- **Use Case**: Removes a package from the virtual environment.
- **Example**: `uv pip uninstall requests` removes the `requests` library.

#### Sync Dependencies with a `requirements.txt` File

```bash
uv pip sync requirements.txt
```

- **Use Case**: Ensures the virtual environment matches the exact packages and versions in `requirements.txt`, removing any unlisted packages.
- **Example**: `uv pip sync requirements.txt` updates the environment to match the file.

## 🙌 Contributions & Feedback

I welcome contributions, suggestions, and feedback!  
If you find any issues or want to improve this project, feel free to open a [GitHub issue](https://github.com/waheed444/Explore-UV/issues) or submit a pull request.

This repo is only for learning and exploring new things, feel free to fork it, explore, or give suggestions!

**Star ⭐ the repo if it helps you!**

---

## 🙌 Let's Connect

<p align="left">
  <a href="https://www.linkedin.com/in/waheed444/?originalSubdomain=pk)" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-blue?style=flat-square&logo=linkedin" alt="LinkedIn">
  </a>
  <a href="https://github.com/waheed444" target="_blank">
    <img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white" alt="GitHub">
  </a>
  <a href="waheedahmad5519@gmail.com" target="_blank">
    <img src="https://img.shields.io/badge/Gmail-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Gmail">
  </a>
</p>

---



    


