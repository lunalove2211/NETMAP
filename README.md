# NETMAP

**NETMAP** is a Linux application that visualizes your entire infrastructure in one place. It gives you a clear map of your hosts, services, and network connections, so you always know what is running and how everything is connected.

## Features

- 🗺️ Full overview of your infrastructure
- 🖥️ Discovers hosts and devices on your network
- 🔌 Shows services, ports, and connections
- ⚡ Lightweight and easy to run
- 🐧 Built for Linux

## Requirements

- Linux (x86_64)
- `tar`
- Root / sudo access (may be required for network scanning)

## Download

Clone the repository:

```bash
git clone https://github.com/lunalove2211/NETMAP.git
cd NETMAP
```

Or download the archive directly from the **Releases** page / repository files.

## Installation

Extract the archive:

```bash
tar -xvf netmap.tar
cd netmap
```

> Replace `netmap.tar` with the actual name of the archive file.

Make the binary executable (if needed):

```bash
chmod +x netmap
```

## Usage

Run the application:

```bash
./netmap
```

With elevated privileges (if required):

```bash
sudo ./netmap
```

### Options

| Option | Description |
|--------|-------------|
| `-h`, `--help` | Show help message |
| `-v`, `--version` | Show version |

> Update this table with your real options.

## Optional: Install system-wide

```bash
sudo mv netmap /usr/local/bin/
netmap
```

## Uninstall

```bash
sudo rm /usr/local/bin/netmap
```

## Troubleshooting

**Permission denied**
Run `chmod +x netmap` and try again.

**Missing results or devices**
Try running with `sudo`.

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

## Author

Created by [lunalove2211](https://github.com/lunalove2211) | PSYHOZ 
