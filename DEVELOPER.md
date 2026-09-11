# Developer documentation

## Validation annotations

The protos carry validation rules in two forms: the legacy
[protoc-gen-validate](https://github.com/bufbuild/protoc-gen-validate) (PGV)
`(validate.rules)` annotations and the
[protovalidate](https://github.com/bufbuild/protovalidate) `(buf.validate.field)`
annotations. PGV is deprecated and its annotations will be removed after downstream
consumers have had time to migrate (see
[cncf/xds#146](https://github.com/cncf/xds/issues/146)). Until then, any new or
changed constraint must be expressed in both forms so that consumers using either
runtime observe the same behavior.

## Synchronize generated files

Run the following command to update the generated files and commit them with your change:

```sh
bazel build //...
tools/generate_go_protobuf.py
```
