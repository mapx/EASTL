load(
    "//config:copts.bzl",
    "EASTL_DEFAULT_COPTS",
    "EASTL_TEST_COPTS",
    "EASTL_EXCEPTIONS_FLAG",
    "EASTL_EXCEPTIONS_FLAG_LINKOPTS",
)

cc_library(
    name = "eatest",
    srcs = glob([
        "source/**/*.cpp",
    ]),
    hdrs = glob([
        "include/EATest/**/*.h",
        "include/EATest/**/*.inl",
    ]),
    copts = EASTL_DEFAULT_COPTS + [
        "-DEASTL_OPENSOURCE=1",
        "-DEASTL_THREAD_SUPPORT_AVAILABLE=0",
    ],
    linkopts = EASTL_EXCEPTIONS_FLAG_LINKOPTS,
    strip_include_prefix = "include",
    visibility = [
        "//visibility:public",
    ],
    deps = [
        "//:eastl",
        "//test/packages/EABase:eabase",
        "//test/packages/EAMain:eamain",
        "//test/packages/EAStdC:eastdc",
        "//test/packages/EAThread:eathread",
    ],
)
