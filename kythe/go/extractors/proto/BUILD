load("@io_kythe//tools:build_rules/shims.bzl", "go_binary")

go_binary(
    name = "extract_proto_kzip",
    srcs = ["extract_proto_kzip.go"],
    visibility = ["//visibility:public"],
    deps = [
        "@io_kythe//kythe/go/extractors/bazel",
        "@io_kythe//kythe/go/extractors/bazel/extutil",
        "@io_kythe//kythe/go/util/vnameutil",
        "@io_kythe//kythe/proto:analysis_go_proto",
        "@org_bitbucket_creachadair_stringset//:go_default_library",
    ],
)

action_listener(
    name = "extract_kzip",
    extra_actions = [":extra_action_kzip"],
    mnemonics = ["GenProtoDescriptorSet"],
    visibility = ["//visibility:public"],
)

extra_action(
    name = "extra_action_kzip",
    cmd = " ".join([
        "$(location :extract_proto_kzip)",
        "--extra_action=$(EXTRA_ACTION_FILE)",
        "--output=$(output $(ACTION_ID).proto.kzip)",
        "--rules=$(location //external:vnames_config)",
        "--language=protobuf",
    ]),
    data = ["//external:vnames_config"],
    out_templates = ["$(ACTION_ID).proto.kzip"],
    tools = [":extract_proto_kzip"],
)
