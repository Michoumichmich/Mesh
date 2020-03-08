# Copyright 2020 The Mesh Authors. All rights reserved.
# Use of this source code is governed by the Apache License,
# Version 2.0, that can be found in the LICENSE file.

workspace(name = 'org_libmesh')

load('@bazel_tools//tools/build_defs/repo:http.bzl', 'http_archive')

commit = {
    'llvm_toolchain': 'e088aaf6cda37ded9768aec85adc2be31725a7af',
    'rules_cc': 'd545fa4f798f2a0b82f556b8b0ec59a93c100df7',
    'googletest': '703bd9caab50b139428cea1aaff9974ebee5742e',
    'heap_layers': 'a80041cc15174ab82a39bae1cd750b52955c7eef',
}

http_archive(
    name = 'rules_cc',
    urls = [
        'https://github.com/bazelbuild/rules_cc/archive/{}.zip'.format(commit['rules_cc']),
    ],
    strip_prefix = 'rules_cc-{}'.format(commit['rules_cc']),
    sha256 = '188e88d911b69bb77b391e02a4a5fdec2313dd01f0305d97cd3451e38f7ace10',
)

http_archive(
    name = 'com_grail_bazel_toolchain',
    urls = [
        'https://github.com/bpowers/bazel-toolchain/archive/{}.zip'.format(commit['llvm_toolchain']),
    ],
    strip_prefix = 'bazel-toolchain-{}'.format(commit['llvm_toolchain']),
    sha256 = '09f02a9ab682e505b058712611fef78681d4d6c5ca0792e342fd95897d958b19',
)

load('@com_grail_bazel_toolchain//toolchain:rules.bzl', 'llvm_toolchain')

llvm_toolchain(
    name = 'llvm_toolchain',
    llvm_version = '9.0.0',
)

load('@llvm_toolchain//:toolchains.bzl', 'llvm_register_toolchains')

llvm_register_toolchains()

http_archive(
    name = 'com_google_googletest',
    urls = [
        'https://github.com/google/googletest/archive/{}.zip'.format(commit['googletest']),
    ],
    strip_prefix = 'googletest-{}'.format(commit['googletest']),
    sha256 = '2db427be8b258ad401177c411c2a7c2f6bc78548a04f1a23576cc62616d9cd38',
)

http_archive(
    name = 'org_heaplayers',
    urls = [
        'https://github.com/emeryberger/Heap-Layers/archive/{}.zip'.format(commit['heap_layers']),
    ],
    strip_prefix = 'Heap-Layers-{}'.format(commit['heap_layers']),
    sha256 = '6b45ed9b771d3f38e5b2cf6e0919eb067762a5e0a9df767c37523a42756341b2',
)