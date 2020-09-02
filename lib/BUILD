load("@io_bazel_rules_rust//rust:rust.bzl", "rust_library")

rust_library(
    name = "lib",
    srcs = ["noop.rs"],
    deps = [
        "//cargo:rusoto_ssm"
    ]
)