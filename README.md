# Sink Protocol

Shared public protocol contracts for Sink services and client libraries.

This module is the source of truth for the canonical record URI and typed key
encoding, plus the versioned Sink gRPC API. It is intentionally limited to
cross-component protocol definitions rather than generic shared utilities.

## Go packages

- `uri` parses and builds canonical `sink://` resource and record addresses.
- `sink/v1` contains the generated `sink.v1` protobuf messages and gRPC API.

Import the package required by your application:

```go
import (
    sink "github.com/batchstream/sink-protocol/sink/v1"
    "github.com/batchstream/sink-protocol/uri"
)
```

## Development

Edit `proto/sink/sink.proto` for public RPC contract changes. Regenerate checked-in
Go bindings with `make proto`; `make proto-check` verifies the generated output.
`proto/sink/sink.proto` uses the stable protobuf package name `sink.v1` and Go
package path `github.com/batchstream/sink-protocol/sink/v1`.
