# Structured Tensors

load("//tensorflow:strict.default.bzl", "py_strict_library", "py_strict_test")

package(
    # copybara:uncomment default_applicable_licenses = ["//tensorflow:license"],
    default_visibility = [
        "//tensorflow:internal",
        "//tensorflow:structured_tensor_allowlist",
    ],
    licenses = ["notice"],
)

py_strict_library(
    name = "structured",
    srcs = ["__init__.py"],
    srcs_version = "PY3",
    tags = ["nofixdeps"],
    deps = [
        ":structured_ops",
    ],
)

py_strict_library(
    name = "structured_ops",
    srcs = ["structured_ops.py"],
    deps = [
        ":structured_array_ops",
        ":structured_tensor",
    ],
)

py_strict_library(
    name = "structured_tensor",
    srcs = [
        "structured_array_ops.py",
        "structured_tensor.py",
    ],
    srcs_version = "PY3",
    deps = [
        "//tensorflow/core/config:flags_py",
        "//tensorflow/python/framework:constant_op",
        "//tensorflow/python/framework:dtypes",
        "//tensorflow/python/framework:extension_type",
        "//tensorflow/python/framework:ops",
        "//tensorflow/python/framework:tensor",
        "//tensorflow/python/framework:tensor_shape",
        "//tensorflow/python/framework:type_spec",
        "//tensorflow/python/ops:array_ops",
        "//tensorflow/python/ops:check_ops",
        "//tensorflow/python/ops:control_flow_ops",
        "//tensorflow/python/ops:math_ops",
        "//tensorflow/python/ops:random_ops",
        "//tensorflow/python/ops/ragged:dynamic_ragged_shape",
        "//tensorflow/python/ops/ragged:ragged_factory_ops",
        "//tensorflow/python/ops/ragged:ragged_tensor",
        "//tensorflow/python/ops/ragged:row_partition",
        "//tensorflow/python/util:compat",
        "//tensorflow/python/util:deprecation",
        "//tensorflow/python/util:dispatch",
        "//tensorflow/python/util:nest",
        "//tensorflow/python/util:tf_export",
        "//third_party/py/numpy",
    ],
)

py_strict_library(
    name = "structured_tensor_dynamic",
    srcs = [
        "structured_tensor_dynamic.py",
    ],
    srcs_version = "PY3",
    deps = [
        ":structured_tensor",
        "//tensorflow/python/framework:tensor",
        "//tensorflow/python/framework:tensor_shape",
        "//tensorflow/python/ops:array_ops",
        "//tensorflow/python/ops/ragged:dynamic_ragged_shape",
    ],
)

py_strict_library(
    name = "structured_array_ops",
    srcs = [
        "structured_array_ops.py",
    ],
    srcs_version = "PY3",
    deps = [
        ":structured_tensor",
        "//tensorflow/core/config:flags_py",
        "//tensorflow/python/framework:constant_op",
        "//tensorflow/python/framework:dtypes",
        "//tensorflow/python/framework:ops",
        "//tensorflow/python/framework:tensor",
        "//tensorflow/python/ops:array_ops",
        "//tensorflow/python/ops:math_ops",
        "//tensorflow/python/ops:random_ops",
        "//tensorflow/python/ops/ragged:dynamic_ragged_shape",
        "//tensorflow/python/ops/ragged:ragged_tensor",
        "//tensorflow/python/ops/ragged:row_partition",
        "//tensorflow/python/util:deprecation",
        "//tensorflow/python/util:dispatch",
    ],
)

py_strict_test(
    name = "structured_tensor_test",
    srcs = ["structured_tensor_test.py"],
    python_version = "PY3",
    deps = [
        ":structured_array_ops",
        ":structured_tensor",
        ":structured_tensor_dynamic",
        "//tensorflow/python/eager:context",
        "//tensorflow/python/framework:constant_op",
        "//tensorflow/python/framework:dtypes",
        "//tensorflow/python/framework:extension_type",
        "//tensorflow/python/framework:ops",
        "//tensorflow/python/framework:sparse_tensor",
        "//tensorflow/python/framework:tensor",
        "//tensorflow/python/framework:tensor_shape",
        "//tensorflow/python/framework:test_lib",
        "//tensorflow/python/ops:array_ops",
        "//tensorflow/python/ops/ragged:dynamic_ragged_shape",
        "//tensorflow/python/ops/ragged:ragged_factory_ops",
        "//tensorflow/python/ops/ragged:ragged_tensor",
        "//tensorflow/python/ops/ragged:row_partition",
        "//tensorflow/python/platform:test",
        "//tensorflow/python/util:dispatch",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
    ],
)

py_strict_test(
    name = "structured_tensor_spec_test",
    srcs = ["structured_tensor_spec_test.py"],
    python_version = "PY3",
    deps = [
        ":structured_tensor",
        "//tensorflow/python/data/ops:dataset_ops",
        "//tensorflow/python/eager:context",
        "//tensorflow/python/framework:dtypes",
        "//tensorflow/python/framework:tensor_shape",
        "//tensorflow/python/framework:tensor_spec",
        "//tensorflow/python/framework:test_lib",
        "//tensorflow/python/framework:type_spec",
        "//tensorflow/python/ops/ragged:dynamic_ragged_shape",
        "//tensorflow/python/ops/ragged:ragged_factory_ops",
        "//tensorflow/python/ops/ragged:ragged_tensor",
        "//tensorflow/python/ops/ragged:row_partition",
        "//tensorflow/python/platform:test",
        "//third_party/py/numpy",
        "@absl_py//absl/testing:parameterized",
    ],
)

py_strict_test(
    name = "structured_array_ops_test",
    srcs = ["structured_array_ops_test.py"],
    python_version = "PY3",
    deps = [
        ":structured_array_ops",
        ":structured_tensor",
        "//tensorflow/python/eager:def_function",
        "//tensorflow/python/framework:dtypes",
        "//tensorflow/python/framework:random_seed",
        "//tensorflow/python/framework:tensor",
        "//tensorflow/python/framework:tensor_shape",
        "//tensorflow/python/framework:test_lib",
        "//tensorflow/python/ops:array_ops",
        "//tensorflow/python/ops:math_ops",
        "//tensorflow/python/ops:random_ops",
        "//tensorflow/python/ops/ragged:dynamic_ragged_shape",
        "//tensorflow/python/ops/ragged:ragged_factory_ops",
        "//tensorflow/python/ops/ragged:ragged_tensor",
        "//tensorflow/python/ops/ragged:row_partition",
        "//tensorflow/python/platform:test",
        "//tensorflow/python/util:nest",
        "@absl_py//absl/testing:parameterized",
    ],
)

py_strict_test(
    name = "structured_tensor_slice_test",
    srcs = ["structured_tensor_slice_test.py"],
    python_version = "PY3",
    deps = [
        ":structured_tensor",
        "//tensorflow/python/framework:constant_op",
        "//tensorflow/python/framework:dtypes",
        "//tensorflow/python/framework:tensor_shape",
        "//tensorflow/python/framework:tensor_spec",
        "//tensorflow/python/framework:test_lib",
        "//tensorflow/python/ops:array_ops",
        "//tensorflow/python/platform:test",
        "@absl_py//absl/testing:parameterized",
    ],
)
