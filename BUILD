cc_library(
    name = "mimc_cpp_sdk",
    copts = [
                "-Os",
                "-fno-omit-frame-pointer",
#                "-fno-rtti",
                "-fno-exceptions",
                "-ffunction-sections",
                "-fdata-sections",
                "-pthread",
#                "-DSTAGING",
    ],
    linkopts = [
        "-lm",
        "-lcrypto",
        "-pthread",
        "-Wl,--gc-sections",
    ],
#    linkstatic = 1,
    includes = ["include"],
    srcs = glob(["src/*.cpp", "src/*.cc", "src/*.c"]),
    hdrs = glob(["include/**/*.h"]),
    deps = [
        "//msg-libs/xmdtransceiver",
        "//third-party/protobuf-2_5_0",
        "//third-party/json-c",
    ]
)

cc_binary(
    name = "mimc_cpp_demo",
    copts = [
         "-Os",
         "-fno-exceptions",
         "-fno-rtti",
         "-ffunction-sections",
         "-fdata-sections",
#         "-DSTAGING",
    ],
    linkopts = [
         "-lz",
         "-lssl",
         "-Wl,--gc-sections",
    ],
    linkstatic=True,
    srcs = ["demo/mimc_demo.cpp"],
    deps = [
        ":mimc_cpp_sdk",
        "//third-party/curl-7-59-0"
    ]
)

cc_binary(
    name = "mimc_av_demo",
    copts = [
         "-Os",
         "-fno-exceptions",
         "-fno-rtti",
         "-ffunction-sections",
         "-fdata-sections",
#        "-DSTAGING",
    ],
    linkopts = [
         "-lz",
         "-lssl",
         "-Wl,--gc-sections",
    ],
    linkstatic=False,
    srcs = ["demo/av_demo.cpp"],
    deps = [
        ":mimc_cpp_sdk",
        "//third-party/curl-7-59-0"
    ]
)

cc_test(
    name = "mimc_cpp_test",
    copts = [
    ],
    linkopts = [
         "-lz",
         "-lssl"
    ],
    srcs = glob([
        "test/mimc_test.cpp"
    ]),
    deps = [
        "//third-party/gtest-170",
        ":mimc_cpp_sdk",
        "//third-party/curl-7-59-0"
    ]
)

cc_test(
    name = "camera_cpp_test",    
    copts = [
        "-Os",
        "-fno-exceptions",
        "-fno-rtti",
        "-ffunction-sections",
        "-fdata-sections",
    ],
    linkopts = [
        "-lz",
        "-lssl",
        "-Wl,--gc-sections",
    ],
    srcs = glob([
       "test/camera_test.cpp" 
    ]),
    deps = [
        "//third-party/gtest-170",
        ":mimc_cpp_sdk",
        "//third-party/curl-7-59-0"
    ]
)