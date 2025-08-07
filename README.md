# Jamixir Release

**Note: This repository contains only compiled releases and binaries. No source code is included here.**



## Usage

After downloading and extracting a release, navigate to the release directory:



### Available Commands

```bash
# Show help
./jamixir --help

# Run the fuzzer
./jamixir fuzzer 

# Generate keys
./jamixir gen-keys
./jamixir gen-keys --file-name my-validator-key

# List existing keys
./jamixir list-keys

# Run a node
./jamixir run
./jamixir run --port 10001
./jamixir run --keys path/to/keys.seed --genesis path/to/genesis.json
```

## Fuzzer

The Jamixir binary includes a built-in fuzzer that runs as a listener on a Unix domain socket.

### Fuzzer Help

```bash
./jamixir fuzzer -h
```

Output:
```
Run the fuzzer listener on unix domain socket

Usage: jamixir fuzzer [OPTIONS]

Options:
     --socket-path <PATH>       Unix domain socket path for fuzzer mode
     --log <LEVEL>              Log level (none | info | warninig | error | debug) default: info
 -h, --help                     Print help

Examples:
 jamixir fuzzer --socket-path ./fuzzer.sock
 jamixir fuzzer --socket-path /tmp/jamixir_fuzzer.sock --log debug
 jamixir fuzzer --log warn --socket-path ./fuzzer.sock
```

### Running the Fuzzer

Basic usage:
```bash
./jamixir fuzzer --socket-path ./fuzzer.sock
```

With custom log level:
```bash
./jamixir fuzzer --socket-path /path/to/socket --log debug
```