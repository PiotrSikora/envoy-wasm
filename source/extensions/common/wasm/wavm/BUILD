licenses(["notice"])  # Apache 2

load(
    "//bazel:envoy_build_system.bzl",
    "envoy_cc_library",
    "envoy_package",
)

envoy_package()

envoy_cc_library(
    name = "wavm_lib",
    srcs = ["wavm.cc"],
    hdrs = ["wavm.h"],
    copts = [
        '-DEMSCRIPTEN_API=""',
        '-DPLATFORM_API=""',
        '-DRUNTIME_API=""',
        '-DLOGGING_API=""',
        '-DWASM_API=""',
        '-DWASTPARSE_API=""',
        '-DIR_API=""',
        "-Wno-non-virtual-dtor",
        "-Wno-old-style-cast",
    ],
    external_deps = [
        "wavm_with_llvm",
    ],
    deps = [
        "//external:abseil_node_hash_map",
        "//include/envoy/server:wasm_interface",
        "//include/envoy/thread_local:thread_local_interface",
        "//source/common/common:assert_lib",
        "//source/common/common:c_smart_ptr_lib",
        "//source/common/protobuf",
        "//source/extensions/common/wasm:wasm_hdr",
        "//source/extensions/common/wasm:well_known_names",
        "@envoy_api//envoy/config/wasm/v2:wasm_cc",
    ],
)
