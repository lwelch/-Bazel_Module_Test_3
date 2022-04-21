load(":ti_toolchain_config.bzl", "ti_toolchain_config")

package(default_visibility = ["//visibility:public"])

config_setting(
    name = "on_linux",
    constraint_values = [
        "@platforms//os:linux",
    ],
)

config_setting(
    name = "on_windows",
    constraint_values = [
        "@platforms//os:windows",
    ],
)

# cc_toolchain_suite(
#     name = "ti_suite",
#     toolchains = {
#         "ti-arm": ":ti_arm_windows_toolchain",
#         "ti-c66": ":ti_c66_windows_toolchain",
#     },
# )

filegroup(name = "empty")

cc_toolchain(
    name = "ti_arm_windows_toolchain",
    all_files = ":empty",
    compiler_files = ":empty",
    dwp_files = ":empty",
    linker_files = ":empty",
    objcopy_files = ":empty",
    strip_files = ":empty",
    supports_param_files = 0,
    toolchain_config = ":ti_arm_windows_toolchain_config",
    toolchain_identifier = "TiArm-toolchain",
)

ti_toolchain_config(
    name = "ti_arm_windows_toolchain_config",
    os = "windows",
)

toolchain(
    name = "ti_arm_windows_cc_toolchain",
    tags = [""],
    target_settings = [],
    toolchain = ":ti_arm_windows_toolchain",
    toolchain_type = "@bazel_tools//tools/cpp:toolchain_type",
    target_compatible_with = ["@platforms//cpu:arm"],
    exec_compatible_with = ["@platforms//os:windows"],
    visibility = ["//visibility:public"],
)
ti_toolchain_config(
    name = "ti_arm_linux_toolchain_config",
    os = "windows",
)

toolchain(
    name = "ti_arm_linux_cc_toolchain",
    tags = [""],
    target_settings = [],
    toolchain = ":ti_arm_linux_toolchain",
    toolchain_type = "@bazel_tools//tools/cpp:toolchain_type",
    target_compatible_with = ["@platforms//cpu:arm"],
    exec_compatible_with = ["@platforms//os:linux"],
    visibility = ["//visibility:public"],
)

cc_toolchain(
    name = "ti_c66_windows_toolchain",
    all_files = ":empty",
    compiler_files = ":empty",
    dwp_files = ":empty",
    linker_files = ":empty",
    objcopy_files = ":empty",
    strip_files = ":empty",
    supports_param_files = 0,
    toolchain_config = ":ti_c66_windows_toolchain_config",
    toolchain_identifier = "TiC66-toolchain",
)

ti_toolchain_config(
    name = "ti_c66_windows_toolchain_config",
    os = "windows",
)

toolchain(
    name = "ti_c66_windows_cc_toolchain",
    tags = [""],
    target_settings = [],
    target_compatible_with = ["@platforms//cpu:ppc"], # Use PPC temporarily, because C66 isn't available
    toolchain = ":ti_c66_toolchain",
    toolchain_type = "@bazel_tools//tools/cpp:toolchain_type",
    exec_compatible_with = ["@platforms//os:windows"],
    visibility = ["//visibility:public"],
)
ti_toolchain_config(
    name = "ti_c66_linux_toolchain_config",
    os = "linux",
)

toolchain(
    name = "ti_c66_linux_cc_toolchain",
    tags = [""],
    target_settings = [],
    target_compatible_with = ["@platforms//cpu:ppc"], # Use PPC temporarily, because C66 isn't available
    toolchain = ":ti_c66_toolchain",
    toolchain_type = "@bazel_tools//tools/cpp:toolchain_type",
    exec_compatible_with = ["@platforms//os:linux"],
    visibility = ["//visibility:public"],
)