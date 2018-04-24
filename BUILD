licenses(["notice"])

exports_files(["LICENSE"])

load(
    "//config:copts.bzl",
    "EASTL_DEFAULT_COPTS",
    "EASTL_TEST_COPTS",
    "EASTL_EXCEPTIONS_FLAG",
    "EASTL_EXCEPTIONS_FLAG_LINKOPTS",
)

cc_library(
    name = "eastl",
    srcs = glob([
        "source/**/*.cpp",
    ]),
    hdrs = glob([
        "include/EASTL/**/*.h",
    ]),
    copts = EASTL_DEFAULT_COPTS + [
        "-D_CHAR16T",
        "-D_CRT_SECURE_NO_WARNINGS",
        "-D_SCL_SECURE_NO_WARNINGS",
        "-DEASTL_OPENSOURCE=1",
    ],
    linkopts = EASTL_EXCEPTIONS_FLAG_LINKOPTS,
    strip_include_prefix = "include",
    visibility = [
        "//visibility:public",
    ],
    deps = [
        "//test/packages/EABase:eabase",
    ],
)

cc_library(
    name = "test",
    srcs = glob(
        [
            "test/source/**/*.cpp",
            "test/source/**/*.h",
        ],
        exclude = [
            "test/source/main.cpp",
        ],
    ),
    hdrs = glob(
        [
            "test/source/**/*.h",
        ],
    ),
    copts = EASTL_TEST_COPTS + [
        "-DEASTL_OPENSOURCE=1",
        "-DEASTL_THREAD_SUPPORT_AVAILABLE=0",
    ],
    linkopts = EASTL_EXCEPTIONS_FLAG_LINKOPTS,
    strip_include_prefix = "test/source",
    textual_hdrs = glob([
        "test/source/**/*.inl",
    ]),
    deps = [
        "//:eastl",
        "//test/packages/EAAssert:eaassert",
        "//test/packages/EABase:eabase",
        "//test/packages/EAMain:eamain",
        "//test/packages/EAStdC:eastdc",
        "//test/packages/EATest:eatest",
        "//test/packages/EAThread:eathread",
    ],
)

cc_binary(
    name = "test-runner",
    srcs = glob([
        "test/source/main.cpp",
    ]),
    copts = EASTL_DEFAULT_COPTS + [
        "-DEASTL_OPENSOURCE=1",
        "-DEASTL_THREAD_SUPPORT_AVAILABLE=0",
    ],
    linkopts = EASTL_EXCEPTIONS_FLAG_LINKOPTS,
    deps = [
        "//:test",
    ],
)

cc_binary(
    name = "benchmark",
    srcs = glob([
        "benchmark/source/**/*.cpp",
        "benchmark/source/**/*.h",
    ]),
    copts = EASTL_DEFAULT_COPTS + [
        "-DEASTL_OPENSOURCE=1",
        "-DEASTL_THREAD_SUPPORT_AVAILABLE=0",
    ],
    linkopts = EASTL_EXCEPTIONS_FLAG_LINKOPTS,
    deps = [
        "//:eastl",
        "//:test",
        "//test/packages/EAStdC:eastdc",
        "//test/packages/EATest:eatest",
    ],
)
