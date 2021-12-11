# bzlmod + rules_nodejs

Part of https://github.com/bazelbuild/rules_nodejs/issues/3138
this repo is just a copy of the `e2e/core` integration test from
<https://github.com/bazelbuild/rules_nodejs/tree/stable/e2e/core>
with the WORKSPACE file mostly replaced by `MODULE.bazel`.

It currently uses this registry
https://github.com/aspect-build/bazel-central-registry/tree/rules_nodejs
for testing, since the upstream BCR doesn't have a rules_nodejs module yet.

## Problems

Currently failing like so:

```
$ bazel test ...
ERROR: /home/alexeagle/.cache/bazel/_bazel_alexeagle/6c8e1f3f909a1683037b3184e9608bb7/external/rules_nodejs.4.4.6.node.node16_toolchains/BUILD.bazel:9:19: While resolving toolchains for target @rules_nodejs.4.4.6.node.node16_toolchains//:resolved_toolchain: no matching toolchains found for types @rules_nodejs.4.4.6//nodejs:toolchain_type
ERROR: Analysis of target '//:use_node_toolchain' failed; build aborted: 
```

There is no toolchain_type for rules_nodejs.4.4.6 repo, I think this needs to be literally `@rules_nodejs//nodejs:toolchain_type` in order to resolve?
