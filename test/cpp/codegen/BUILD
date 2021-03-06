# Copyright 2017 gRPC authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

licenses(["notice"])  # Apache v2

load("//bazel:grpc_build_system.bzl", "grpc_cc_test", "grpc_package", "grpc_cc_binary", "grpc_sh_test")

grpc_package(name = "test/cpp/codegen")

grpc_cc_test(
    name = "codegen_test_full",
    srcs = ["codegen_test_full.cc"],
    deps = [
        "//:grpc++",
        "//test/core/util:gpr_test_util",
    ],
    external_deps = [
        "gtest",
    ],
)

grpc_cc_test(
    name = "codegen_test_minimal",
    srcs = ["codegen_test_minimal.cc"],
    deps = [
        "//:grpc++",
        "//test/core/util:gpr_test_util",
    ],
    external_deps = [
        "gtest",
    ],
)

grpc_cc_test(
    name = "proto_utils_test",
    srcs = ["proto_utils_test.cc"],
    deps = [
        "//:grpc++",
        "//test/core/util:gpr_test_util",
    ],
    external_deps = [
        "gtest",
        "protobuf",
    ],
)

grpc_cc_binary(
    name = "golden_file_test",
    testonly = True,
    srcs = ["golden_file_test.cc"],
    deps = [
        "//:grpc++",
        "//src/proto/grpc/testing:compiler_test_proto",
        "//test/core/util:gpr_test_util",
    ],
    external_deps = [
        "gtest",
        "gflags",
    ],
)

grpc_sh_test(
    name = "run_golden_file_test",
    srcs = ["run_golden_file_test.sh"],
    data = [
        ":golden_file_test",
        ":compiler_test_golden",
        ":compiler_test_mock_golden",
        "//src/proto/grpc/testing:_compiler_test_proto_grpc_codegen",
    ],
)
