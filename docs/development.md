# Development

If you'd like to contribute to Regal, here are some pointers to help get you started.

## Building

1. Run the `build.sh` script to populate the `data` directory with any data necessary for linting (such as the built-in
   function metadata from OPA)
2. Build the `regal` executable by running `go build`

## Testing

To run all tests, including the Rego rules unit tests:

```shell
go test ./...
```

## Linting

Regal uses [golangci-lint](https://golangci-lint.run/) with most linters enabled. In order to check your code, run:

```shell
golangci-lint run ./...
```

In order to please the [gci](https://github.com/daixiang0/gci) linter, you may either manually order imports, or have
them automatically ordered and grouped by the tool:

```shell
gci write \
  -s standard \
  -s default \
  -s "prefix(github.com/open-policy-agent/opa)" \
  -s "prefix(github.com/styrainc/regal)" \
  -s blank \
  -s dot .
```