# reproduce-rules-python-bug

bazel run //:go

## Problem

The python package is correctly installed in `bazel-reproduce-rules-python-bug/external/my_deps_torch_tensorrt/site-packages/`. However, this dependency will not be copied in the runfiles director (`bazel-bin/go.runfiles/my_deps_torch_tensorrt/site-packages/`)
