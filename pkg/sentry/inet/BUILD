load("@io_bazel_rules_go//go:def.bzl", "go_library")

package(
    default_visibility = ["//:sandbox"],
    licenses = ["notice"],  # Apache 2.0
)

load("//tools/go_stateify:defs.bzl", "go_stateify")

go_stateify(
    name = "inet_state",
    srcs = ["inet.go"],
    out = "inet_state.go",
    package = "inet",
)

go_library(
    name = "inet",
    srcs = [
        "inet.go",
        "inet_state.go",
        "test_stack.go",
    ],
    importpath = "gvisor.googlesource.com/gvisor/pkg/sentry/inet",
    deps = [
        "//pkg/state",
    ],
)
