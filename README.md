# NETMAP

**NETMAP** is a terminal (TUI) application for Linux that shows your entire infrastructure in one place: processes, ports, and network connections. Built with Python, [Textual](https://github.com/Textualize/textual) and [psutil](https://github.com/giampaolo/psutil).

## Features

- 🗺️ Full overview of your infrastructure right in the terminal
- 🔌 Processes, ports, and active network connections
- ⚡ Lightweight, no GUI required
- 🐧 Built for Linux

## Requirements

- Linux
- **Python 3.11 or newer** (see [Installing Python 3.11](#installing-python-311) if you have an older version)
- `git`, `pip`, `tar`
- Root access (optional, for the full picture, see [Usage](#usage))

Check your Python version:

```bash
python3 --version
```

## Installing Python 3.11

Skip this step if `python3 --version` already shows 3.11 or higher.

### Option A: uv (recommended, works on any distro, no apt needed)

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
source ~/.local/bin/env
```

`uv` downloads Python 3.11 automatically in the next steps.

### Option B: Ubuntu / Debian (deadsnakes PPA)

```bash
sudo apt update
sudo apt install -y software-properties-common
sudo add-apt-repository -y ppa:deadsnakes/ppa
sudo apt update
sudo apt install -y python3.11 python3.11-venv
python3.11 --version
```

### Option C: Fedora

```bash
sudo dnf install -y python3.11
```

## Installation

### 1. Download

```bash
git clone https://github.com/lunalove2211/NETMAP.git
cd NETMAP
```

### 2. Extract the archive

The project is distributed as `netmap.tar.gz`:

```bash
tar -xzvf netmap.tar.gz
cd netmap
```

### 3. Create a virtual environment and install

**With uv:**

```bash
uv venv --python 3.11 .venv
source .venv/bin/activate
uv pip install -e .
```

**With system Python 3.11:**

```bash
python3.11 -m venv .venv
source .venv/bin/activate
pip install -e .
```

Dependencies (`psutil`, `textual`) are installed automatically.

## Usage

### Running after re-login

The virtual environment is not activated automatically in new sessions:

```bash
cd NETMAP/netmap
source .venv/bin/activate
netmap
```

Or install a global shortcut once:

```bash
sudo ln -s "$(pwd)/.venv/bin/netmap" /usr/local/bin/netmap
```

After that, `netmap` (or `sudo netmap`) works from anywhere.

Run the app:

```bash
netmap
```

### Running as root (recommended)

Without root, PIDs and process info of other users will show as `N/A`. For the full picture, run:

```bash
sudo .venv/bin/netmap
```

> `sudo netmap` may not work inside a virtual environment, because `sudo` does not use the venv's `PATH`. Use the full path to the binary as shown above.

## Updating

```bash
cd NETMAP
git pull
tar -xzvf netmap.tar.gz
cd netmap
source .venv/bin/activate
pip install -e .
```

## Uninstall

```bash
deactivate
cd ../..
rm -rf NETMAP
```

## Troubleshooting

**`ERROR: Package 'netmap' requires a different Python: 3.10.x not in '>=3.11'`**
Your Python is too old. Install Python 3.11 (see [Installing Python 3.11](#installing-python-311)), then recreate the virtual environment:

```bash
deactivate
rm -rf .venv
python3.11 -m venv .venv   # or: uv venv --python 3.11 .venv
source .venv/bin/activate
pip install -e .
```

**`tar: netmap.tar: Cannot open`**
The archive is named `netmap.tar.gz`. Use `tar -xzvf netmap.tar.gz`.

**`does not appear to be a Python project: neither 'setup.py' nor 'pyproject.toml' found`**
You are in the wrong folder. Extract the archive first and run `pip install -e .` from the directory that contains `pyproject.toml`.

**`netmap: command not found`**
Make sure the virtual environment is activated: `source .venv/bin/activate`

**Warning: running without root**
Some process info will be unavailable. Run with `sudo .venv/bin/netmap`.

**`Could not get lock /var/lib/dpkg/lock-frontend` (Ubuntu/Debian)**
Another package process (usually `unattended-upgrade`) is running. Wait for it to finish, or use Option A (uv) to install Python without apt.

**`python3 -m venv` fails on Debian/Ubuntu**
Install the venv package: `sudo apt install python3-venv`

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

## Author

Created by [lunalove2211](https://github.com/lunalove2211) | PSYHOZ
