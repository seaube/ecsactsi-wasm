workspace(name = "ecsactsi_wasm")

load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "ecsact_lang_cpp",
    sha256 = "b06ebbbb9ed87dad1c997dc08cd608e9dcf7df652922505eea8c54907b027607",
    strip_prefix = "ecsact_lang_cpp-0195aae568e8c1c3de0e74bcd2ea215b0629e96b",
    url = "https://github.com/ecsact-dev/ecsact_lang_cpp/archive/0195aae568e8c1c3de0e74bcd2ea215b0629e96b.zip",
)

http_archive(
    name = "rules_ecsact",
    sha256 = "8cfdc8395502ae8d764611d0b6911d26461dc41511151675ccc019d9ebe723c5",
    strip_prefix = "rules_ecsact-0.1.5",
    url = "https://github.com/ecsact-dev/rules_ecsact/archive/refs/tags/0.1.5.tar.gz",
)

load("@rules_ecsact//ecsact:repositories.bzl", "ecsact_register_toolchains", "rules_ecsact_dependencies")

rules_ecsact_dependencies()

ecsact_register_toolchains()

http_archive(
    name = "ecsact_rt_entt",
    sha256 = "a41ff69de20b63f1abbf4577fbfc3a9581272d1bf93d72113e7511f14fc45067",
    strip_prefix = "ecsact_rt_entt-46bbcf6b93c52e808aba4769b5f65df1f4ecc0e9",
    urls = ["https://github.com/ecsact-dev/ecsact_rt_entt/archive/46bbcf6b93c52e808aba4769b5f65df1f4ecc0e9.zip"],
)

http_archive(
    name = "com_github_skypjack_entt",
    sha256 = "f7031545130bfc06f5fe6b2f8c87dcbd4c1254fab86657e2788b70dfeea57965",
    strip_prefix = "entt-3.10.1",
    url = "https://github.com/skypjack/entt/archive/refs/tags/v3.10.1.tar.gz",
)

http_archive(
    name = "boost",
    sha256 = "c41441a6e9f8038ad626e9f937ddc3675ab896b6c3512eefc6840037b3816d03",
    strip_prefix = "boost-563e8e0de4eac4b48a02d296581dc2454127608e",
    urls = ["https://github.com/bazelboost/boost/archive/563e8e0de4eac4b48a02d296581dc2454127608e.zip"],
)

load("@boost//:index.bzl", "boost_http_archives")

boost_http_archives()

_nlohmann_json_build_file = """
load("@rules_cc//cc:defs.bzl", "cc_library")

cc_library(
    name = "json",
    visibility = ["//visibility:public"],
    includes = ["include"],
    hdrs = glob(["include/**/*.hpp"]),
    strip_include_prefix = "include",
)
"""

http_archive(
    name = "nlohmann_json",
    build_file_content = _nlohmann_json_build_file,
    sha256 = "62c585468054e2d8e7c2759c0d990fd339d13be988577699366fe195162d16cb",
    url = "https://github.com/nlohmann/json/releases/download/v3.10.4/include.zip",
)

http_archive(
    name = "com_google_protobuf",
    sha256 = "7308590dbb95e77066b99c5674eed855c8257e70658d2af586f4a81ff0eea2b1",
    strip_prefix = "protobuf-3.18.0",
    urls = ["https://github.com/protocolbuffers/protobuf/releases/download/v3.18.0/protobuf-cpp-3.18.0.tar.gz"],
)

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()

http_archive(
    name = "com_grail_bazel_toolchain",
    sha256 = "644b7c35adbfbf312d86176660a196e67e7a2c3f20114941a60d0379f2b4771f",
    strip_prefix = "bazel-toolchain-9e71d562023dc7994e747110ee1ca345ad6b4413",
    url = "https://github.com/grailbio/bazel-toolchain/archive/9e71d562023dc7994e747110ee1ca345ad6b4413.zip",
)

load("@com_grail_bazel_toolchain//toolchain:deps.bzl", "bazel_toolchain_dependencies")

bazel_toolchain_dependencies()

load("@com_grail_bazel_toolchain//toolchain:rules.bzl", "llvm_toolchain")

llvm_toolchain(
    name = "llvm_toolchain",
    cxx_standard = {"linux": "c++20"},
    llvm_version = "14.0.0",
)

load("@llvm_toolchain//:toolchains.bzl", "llvm_register_toolchains")

llvm_register_toolchains()

http_archive(
    name = "ecsact_runtime",
    sha256 = "b5935092ef9a59e1bb328754bd9f7da8cd42f32b698a5c140a6a4a1f158aa38c",
    strip_prefix = "ecsact_runtime-c7dd47db3e0c5ad565e4c17d94a4eb36b95f39a4",
    url = "https://github.com/ecsact-dev/ecsact_runtime/archive/c7dd47db3e0c5ad565e4c17d94a4eb36b95f39a4.zip",
)

git_repository(
    name = "ecsact_entt",
    commit = "47fdb9612d2f1273592aeb3434c2b3110662c9b7",
    remote = "git@github.com:seaube/ecsact-entt.git",
)

load("//:wasmer.bzl", "wasmer_repo")

wasmer_repo(name = "wasmer")

http_archive(
    name = "magic_enum",
    sha256 = "5e7680e877dd4cf68d9d0c0e3c2a683b432a9ba84fc1993c4da3de70db894c3c",
    strip_prefix = "magic_enum-0.8.0",
    urls = ["https://github.com/Neargye/magic_enum/archive/refs/tags/v0.8.0.tar.gz"],
)

http_archive(
    name = "hedron_compile_commands",
    sha256 = "cb29ade67efd170c98b86fe75524fc053c01dcbe1f6211d00ce658e57441ed42",
    strip_prefix = "bazel-compile-commands-extractor-670e86177b6b5c001b03f4efdfba0f8019ff523f",
    url = "https://github.com/hedronvision/bazel-compile-commands-extractor/archive/670e86177b6b5c001b03f4efdfba0f8019ff523f.tar.gz",
)

load("@hedron_compile_commands//:workspace_setup.bzl", "hedron_compile_commands_setup")

hedron_compile_commands_setup()

http_archive(
    name = "emsdk",
    sha256 = "a755b38d5f5c6e5d73ff0f08dc9f7f2e0305230a5585cac82a02064740e93303",
    strip_prefix = "emsdk-50586ea897efd496f94ddf55236fbdd54c60465c/bazel",
    url = "https://github.com/zaucy/emsdk/archive/50586ea897efd496f94ddf55236fbdd54c60465c.zip",
)

load("@emsdk//:deps.bzl", emsdk_deps = "deps")

emsdk_deps()

load("@emsdk//:emscripten_deps.bzl", emsdk_emscripten_deps = "emscripten_deps")

emsdk_emscripten_deps()

load("@emsdk//:toolchains.bzl", "register_emscripten_toolchains")

register_emscripten_toolchains()
