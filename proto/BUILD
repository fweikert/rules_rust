package(default_visibility = ["//visibility:public"])

load("@bazel_skylib//:bzl_library.bzl", "bzl_library")
load(":toolchain.bzl", "rust_proto_toolchain")

alias(
    name = "protoc_gen_rust",
    actual = "//proto/raze:cargo_bin_protoc_gen_rust",
)

alias(
    name = "protoc_gen_rust_grpc",
    actual = "//proto/raze:cargo_bin_protoc_gen_rust_grpc",
)

toolchain_type(name = "toolchain")

py_binary(
    name = "optional_output_wrapper",
    srcs = ["optional_output_wrapper.py"],
)

toolchain(
    name = "default-proto-toolchain",
    toolchain = ":default-proto-toolchain-impl",
    toolchain_type = "@io_bazel_rules_rust//proto:toolchain",
)

rust_proto_toolchain(name = "default-proto-toolchain-impl")

bzl_library(
    name = "rules",
    srcs = glob(["**/*.bzl"]),
)
