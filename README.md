# NETMAP

**NETMAP** is a terminal (TUI) application for Linux that shows your entire infrastructure in one place: processes, ports, and network connections. Built with Python, [Textual](https://github.com/Textualize/textual) and [psutil](https://github.com/giampaolo/psutil).

## Features

- 🗺️ Full overview of your infrastructure in the terminal
- 🔌 Processes, ports, and active network connections
- ⚡ Lightweight, no GUI required
- 🐧 Built for Linux

## Requirements

- Linux
- Python 3.9+
- `git` and `pip`
- Root access (optional, for the full picture, see below)

## Installation

### 1. Download

```bash
git clone https://github.com/lunalove2211/NETMAP.git
cd NETMAP
```

Or download the `.tar` archive and extract it:

```bash
tar -xvf netmap.tar
cd netmap
```

### 2. Create a virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install

```bash
pip install -e .
```

This will automatically install the dependencies: `psutil` and `textual`.

## Usage

Run the app:

```bash
netmap
```

### Running with root (recommended)

Without root, PIDs and process info of other users will show as `N/A`. For the full picture, run:

```bash
sudo .venv/bin/netmap
```

> `sudo netmap` may not work from inside a virtual environment, because `sudo` does not use the venv's `PATH`. Use the full path to the binary as shown above.

## Updating

```bash
cd NETMAP
git pull
source .venv/bin/activate
pip install -e .
```

## Uninstall

```bash
deactivate
rm -rf NETMAP
```

## Troubleshooting

**`netmap: command not found`**
Make sure the virtual environment is activated: `source .venv/bin/activate`

**Warning: running without root**
Some process info will be unavailable. Run with `sudo .venv/bin/netmap`.

**`python3 -m venv` fails on Debian/Ubuntu**
Install the venv package: `sudo apt install python3-venv`

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

## Author

Created by [lunalove2211](https://github.com/lunalove2211) | PSTHOZ
