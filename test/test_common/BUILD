licenses(["notice"])  # Apache 2

load(
    "//bazel:envoy_build_system.bzl",
    "envoy_cc_library",
    "envoy_basic_cc_library",
    "envoy_cc_test_library",
    "envoy_package",
)

envoy_package()

envoy_basic_cc_library(
    name = "printers_includes",
    hdrs = ["printers.h"],
)

envoy_cc_test_library(
    name = "environment_lib",
    srcs = ["environment.cc"],
    hdrs = ["environment.h"],
    deps = [
        ":network_utility_lib",
        "//include/envoy/server:options_interface",
        "//source/common/common:assert_lib",
        "//source/common/common:compiler_requirements_lib",
        "//source/common/common:macros",
        "//source/common/common:utility_lib",
        "//source/common/json:json_loader_lib",
        "//source/common/network:utility_lib",
        "//source/server:options_lib",
    ],
)

envoy_cc_test_library(
    name = "network_utility_lib",
    srcs = ["network_utility.cc"],
    hdrs = ["network_utility.h"],
    deps = [
        ":utility_lib",
        "//source/common/common:assert_lib",
        "//source/common/network:address_lib",
        "//source/common/network:utility_lib",
        "//source/common/runtime:runtime_lib",
    ],
)

envoy_cc_library(
    name = "printers_lib",
    srcs = ["printers.cc"],
    deps = [
        ":printers_includes",
        "//source/common/buffer:buffer_lib",
        "//source/common/http:header_map_lib",
        "//source/common/redis:codec_lib",
    ],
)

envoy_cc_test_library(
    name = "registry_lib",
    hdrs = ["registry.h"],
    deps = [
        "//include/envoy/registry",
    ],
)

envoy_cc_test_library(
    name = "utility_lib",
    srcs = ["utility.cc"],
    hdrs = ["utility.h"],
    external_deps = ["envoy_bootstrap"],
    deps = [
        "//include/envoy/buffer:buffer_interface",
        "//include/envoy/http:codec_interface",
        "//include/envoy/network:address_interface",
        "//source/common/common:empty_string",
        "//source/common/config:bootstrap_json_lib",
        "//source/common/http:header_map_lib",
        "//source/common/json:json_loader_lib",
        "//source/common/network:address_lib",
        "//source/common/network:utility_lib",
        "//source/common/protobuf:utility_lib",
    ],
)

envoy_cc_test_library(
    name = "lua_wrappers_lib",
    hdrs = ["lua_wrappers.h"],
    deps = [
        "//test/mocks/thread_local:thread_local_mocks",
    ],
)

envoy_cc_library(
    name = "threadsafe_singleton_injector_lib",
    hdrs = ["threadsafe_singleton_injector.h"],
    deps = [
        "//source/common/singleton:threadsafe_singleton",
    ],
)
