workspace(name = "io_kythe_lang_proto")

load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "bazel_toolchains",
    sha256 = "0ffaab86bed3a0c8463dd63b1fe2218d8cad09e7f877075bf028f202f8df1ddc",
    strip_prefix = "bazel-toolchains-5ce127aee3b4c22ab76071de972b71190f29be6e",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-toolchains/archive/5ce127aee3b4c22ab76071de972b71190f29be6e.tar.gz",
        "https://github.com/bazelbuild/bazel-toolchains/archive/5ce127aee3b4c22ab76071de972b71190f29be6e.tar.gz",
    ],
)

git_repository(
    name = "io_kythe",
    commit = "4f5e9730130cfc799b87e7e7a7b3d13d7b60a3a4",
    remote = "https://github.com/kythe/kythe",
)

load("@io_kythe//:setup.bzl", "kythe_rule_repositories")

kythe_rule_repositories()

load("@io_kythe//:external.bzl", "kythe_dependencies")

kythe_dependencies()
