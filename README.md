# Audit Contract

This repository contains the source Protobuf definition for the audit service API.

## Purpose

The contract defines the request and response payloads shared between the backend and the audit service. It acts as the stable API boundary for audit logging operations.

## Files

- proto/audit.proto: source contract definition
- proto/audit.pb.go: generated Go types
- proto/audit_grpc.pb.go: generated gRPC client/server bindings

## How to regenerate

If the proto file changes, regenerate the Go bindings with the protobuf toolchain used by your Go environment.

```bash
protoc --go_out=. --go-grpc_out=. proto/audit.proto
```

## Relationship to the project

- backend-api depends on this contract through the sibling audit-contracts module
- audit-service consumes the generated Go types via the shared contracts package

## Notes

Keep the proto schema backward compatible when changing message fields or RPC definitions.
