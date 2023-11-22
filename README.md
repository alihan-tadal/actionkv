# ActionKV Memory Store

`akv_mem` is a simple key-value store with basic CRUD operations, implemented in Rust. It uses a custom file format to persist data and provides a command-line interface for interacting with the store.

## Usage

```bash
akv_mem FILE get KEY
akv_mem FILE delete KEY
akv_mem FILE insert KEY VALUE
akv_mem FILE update KEY VALUE
```

### Example

```bash
akv_mem data.db get my_key
akv_mem data.db insert my_key "Hello, World!"
akv_mem data.db update my_key "Updated Value"
akv_mem data.db delete my_key
```

## Command-Line Options

- `get KEY`: Retrieves the value associated with the specified key.
- `delete KEY`: Deletes the entry with the specified key.
- `insert KEY VALUE`: Inserts a new key-value pair into the store.
- `update KEY VALUE`: Updates the value associated with the specified key.

## Building

Make sure you have [Rust](https://www.rust-lang.org/tools/install) installed.

```bash
cargo build --release
```

## Running

```bash
cargo run -- FILE get KEY
cargo run -- FILE delete KEY
cargo run -- FILE insert KEY VALUE
cargo run -- FILE update KEY VALUE
```

## Library (`libactionkv`) Usage

```rust
use libactionkv::ActionKV;

// Example code using the ActionKV library
```

## File Format

The key-value store uses a custom file format to persist data. Each entry is stored with a checksum, key length, value length, and the actual key-value data.

## Dependencies

- [byteorder](https://crates.io/crates/byteorder): Read and write numbers in little-endian or big-endian order.
- [crc](https://crates.io/crates/crc): Cyclic Redundancy Check (CRC) calculation.
- [serde](https://crates.io/crates/serde): Serialization and deserialization framework for Rust.
