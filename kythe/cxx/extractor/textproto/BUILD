cc_binary(
    name = "textproto_extractor",
    srcs = ["textproto_extractor.cc"],
    visibility = ["//visibility:public"],
    deps = [
        ":textproto_schema",
        "//kythe/cxx/extractor/proto:lib",
        "//kythe/cxx/indexer/proto:search_path",
        "@com_github_gflags_gflags//:gflags",
        "@com_github_google_glog//:glog",
        "@com_google_absl//absl/strings",
        "@io_kythe//kythe/cxx/common:kzip_writer",
        "@io_kythe//kythe/proto:analysis_cc_proto",
    ],
)

cc_library(
    name = "textproto_schema",
    srcs = ["textproto_schema.cc"],
    hdrs = ["textproto_schema.h"],
    deps = [
        "@com_google_absl//absl/strings",
    ],
)

cc_test(
    name = "textproto_schema_test",
    srcs = ["textproto_schema_test.cc"],
    deps = [
        ":textproto_schema",
        "@io_kythe//third_party:gtest_main",
    ],
)
