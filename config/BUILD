load(":compiler_config_setting.bzl", "create_llvm_config")

create_llvm_config(
    name = "llvm_compiler",
    visibility = ["//:__subpackages__"],
)

# following configs are based on mapping defined in: https://git.io/v5Ijz
config_setting(
    name = "ios",
    values = {
        "cpu": "darwin",
    },
    visibility = ["//:__subpackages__"],
)

config_setting(
    name = "windows",
    values = {
        "cpu": "x64_windows",
    },
    visibility = ["//:__subpackages__"],
)

config_setting(
    name = "ppc",
    values = {
        "cpu": "ppc",
    },
    visibility = ["//:__subpackages__"],
)


