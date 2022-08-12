WORKSPACE_NAME = "TestWork"

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive", "http_file")


http_archive(
    name = "rules_python",
    sha256 = "0781b87806f4e2f228b18e23451cc63d799acfeb78e7de77879ce0ef6f76126d",
    strip_prefix = "rules_python-c9b70d1d14a18e19607c7610127ffacb43855dba",
    url = "https://github.com/bazelbuild/rules_python/archive/c9b70d1d14a18e19607c7610127ffacb43855dba.zip",
)

load("@rules_python//python:repositories.bzl", "python_register_toolchains")
load("@rules_python//python:pip.bzl", "pip_parse")


python_register_toolchains(
    name = "python_runtime",
    # Available versions are listed in @rules_python//python:versions.bzl.
    python_version = "3.8.12",
)

load("@python_runtime//:defs.bzl", python_interpreter = "interpreter")

pip_parse(
    name = "my_deps",
    python_interpreter_target = python_interpreter,
    requirements_lock = "//:requirements.txt.lock",
)

load("@my_deps//:requirements.bzl", "install_deps")
# Call it to define repos for your requirements.
install_deps()