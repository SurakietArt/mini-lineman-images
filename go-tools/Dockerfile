# golang:1.27.1 — resolved 2026-10-07. Bump via the digest, never the tag.
FROM golang@sha256:162be5298a40ed317005c8339c6de4d10d3eef336d66dc8e9259b03ab9d3a6d2

# Install tools BEFORE locking the toolchain: some tools' own go.mod
# requires a newer Go, and GOTOOLCHAIN=local would refuse to build them.
RUN go install github.com/golangci/golangci-lint/v2/cmd/golangci-lint@v2.14.0

# ADR 0001 decision 3: the image decides the Go version, not each service's go.mod.
# A repo requiring newer Go now fails loudly instead of silently downloading it.
ENV GOTOOLCHAIN=local

WORKDIR /src

