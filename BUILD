load("@my_deps//:requirements.bzl", "requirement")
load("@rules_python//python:defs.bzl", "py_binary")

py_binary(
    name = "go",
    srcs = ["go.py"],
    deps = [
        requirement("torch_tensorrt"),
    ],
)
