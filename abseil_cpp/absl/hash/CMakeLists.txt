#
# Copyright 2018 The Abseil Authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      https://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

absl_cc_library(
  NAME
    hash
  HDRS
    "hash.h"
  SRCS
    "internal/hash.cc"
    "internal/hash.h"
  COPTS
    ${ABSL_DEFAULT_COPTS}
  DEPS
    absl_core_headers
    absl_endian
    absl_fixed_array
    absl_meta
    absl_int128
    absl_strings
    absl_optional
    absl_variant
    absl_utility
    absl_city
  PUBLIC
)

absl_cc_library(
  NAME
    hash_testing
  HDRS
    "hash_testing.h"
  COPTS
    ${ABSL_TEST_COPTS}
  DEPS
    absl_spy_hash_state
    absl_meta
    absl_strings
    absl_variant
    gmock
  TESTONLY
)

absl_cc_test(
  NAME
    hash_test
  SRCS
    "hash_test.cc"
  COPTS
    ${ABSL_TEST_COPTS}
  DEPS
    absl_hash
    absl_hash_testing
    absl_core_headers
    absl_flat_hash_set
    absl_spy_hash_state
    absl_meta
    absl_int128
    gmock_main
)

absl_cc_library(
  NAME
    spy_hash_state
  HDRS
    "internal/spy_hash_state.h"
  COPTS
    ${ABSL_DEFAULT_COPTS}
  DEPS
    absl_hash
    absl_strings
    absl_str_format
  TESTONLY
)

absl_cc_library(
  NAME
    city
  HDRS
    "internal/city.h"
  SRCS
    "internal/city.cc"
  COPTS
    ${ABSL_DEFAULT_COPTS}
  DEPS
    absl_config
    absl_core_headers
    absl_endian
)

absl_cc_test(
  NAME
    city_test
  SRCS
    "internal/city_test.cc"
  COPTS
    ${ABSL_TEST_COPTS}
  DEPS
    absl_city
    gmock_main
)

