# bzlmod + rules_nodejs

Part of https://github.com/bazelbuild/rules_nodejs/issues/3138
this repo is just a copy of the `e2e/core` integration test from
<https://github.com/bazelbuild/rules_nodejs/tree/stable/e2e/core>
with the WORKSPACE file mostly replaced by `MODULE.bazel`.

It currently uses this registry
https://github.com/aspect-build/bazel-central-registry/tree/rules_nodejs
for testing, since the upstream BCR doesn't have a rules_nodejs module yet.
