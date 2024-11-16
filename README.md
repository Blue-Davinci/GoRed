# GoRed: An In-Memory Redis-like Server in Go

GoRedis is a lightweight, in-memory key-value store implemented in Go, inspired by Redis. This project demonstrates building a simple yet functional key-value store with basic command support, such as `SET`, `GET`, and `HELLO`. 

## Features
- **In-Memory Key-Value Storage**: Store and retrieve data efficiently without persistence.
- **RESP Protocol Support**: Implements a subset of the Redis Serialization Protocol (RESP).
- **Concurrent Connections**: Handle multiple clients concurrently with Go's goroutines and channels.
- **Configurable Server**: Easily configure the listening address for the server.
- **Integration Testing**: Includes tests using the official Redis Go client.

## Requirements
- [Go 1.20+](https://golang.org/dl/) for building and running the server.

## Getting Started

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/Blue-Davinci/GoRed.git
   cd goredis
2. Use the provided `makefile` to build and run the server:
- Build the server:
```bash
make build
```
This will compile the server and place the binary in the bin/ directory.
- Run the server:
```bash
make run
```
By default, the server will listen on :5001. You can customize this address in the Makefile or pass it as an argument.

## Usage
1. Start the server:
   ```bash
   make run
   ```
2. Connect using redis-cli:
```bash
redis-cli -p 5001
```
3. Interact with the server:
```bash
127.0.0.1:5001> SET name GoRedis
OK
127.0.0.1:5001> GET name
"GoRedis"
127.0.0.1:5001> HELLO
1) "server"
2) "redis"
```

<br />

## Project Structure

```markdown
- **`main.go`**: Entry point of the server.
- **`keyval.go`**: Implementation of the in-memory key-value store.
- **`peer.go`**: Manages client connections.
- **`proto.go`**: Protocol logic for RESP commands.
- **`proto_test.go`**: Placeholder for testing protocol functionality.
- **`server_test.go`**: Integration tests using the official Redis client.
```
# Development
## Prerequisites
Install the dependencies using:
```bash
go mod tidy
```
### Running Tests
Run the tests using:
```bash
go test ./...
```
## Configuration
The server can be configured using command-line flags:
```bash
- `--listenAddr`: Specifies the address on which the server listens for connections. Default is `:5001`.
```


Contributions are welcome! If you have ideas for improvements or encounter issues, feel free to open an issue or a pull request.
License

This project is licensed under the MIT License.

Enjoy using GoRedis! 🚀
