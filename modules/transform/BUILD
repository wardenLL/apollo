load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "tf2_buffer_lib",
    srcs = [
        "buffer.cc",
    ],
    hdrs = [
        "buffer_interface.h",
        "buffer.h",
    ],
    deps = [
        "//cyber",
        "//modules/transform/proto:transform_proto",
        "//third_party/tf2:tf2"
    ],
)
cc_library(
    name = "transform_broadcaster_lib",
    srcs = [
        "transform_broadcaster.cc",
    ],
    hdrs = [
        "transform_broadcaster.h",
    ],
    deps = [
        "//cyber",
        "//modules/transform/proto:transform_proto",
        "//third_party/tf2:tf2"
    ],
)

cc_library(
    name = "static_transform_component_lib",
    srcs = [
        "static_transform_component.cc",
    ],
    hdrs = [
        "static_transform_component.h",
    ],
    deps = [
        "//cyber",
        "//modules/common/util:file_util",
        "//modules/transform/proto:static_transform_conf_proto",
        "//modules/transform/proto:transform_proto",
        "//third_party/tf2:tf2",
        "@yaml_cpp//:yaml"
    ],
    copts = ['-DMODULE_NAME=\\"static_transform\\"']
)

cc_binary(
    name = "libstatic_transform_component.so",
    deps = [":static_transform_component_lib"],
    linkshared = True,
    linkstatic = False,
)



cpplint()
