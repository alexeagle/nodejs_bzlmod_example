load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "npm_acorn-8.5.0",
    build_file_content = """
load("@rules_nodejs//third_party/github.com/bazelbuild/bazel-skylib:rules/copy_file.bzl", "copy_file")

# Turn a source directory into a TreeArtifact for RBE-compat
copy_file(
    name = "npm_acorn-8.5.0",
    src = "package",
    # This attribute comes from rules_nodejs patch of
    # https://github.com/bazelbuild/bazel-skylib/pull/323
    is_directory = True,
    # We must give this as the directory in order for it to appear on NODE_PATH
    out = "acorn",
    visibility = ["//visibility:public"],
)
""",
    sha256 = "d8f9d40c4656537a60bf0c6daae6f0553f54df5ff2518f86464b7c785f20376b",
    urls = ["https://registry.npmjs.org/acorn/-/acorn-8.5.0.tgz"],
)
