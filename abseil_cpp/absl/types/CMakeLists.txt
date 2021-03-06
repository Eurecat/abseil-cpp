#
# Copyright 2017 The Abseil Authors.
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
    any
  HDRS
    "any.h"
  COPTS
    ${ABSL_DEFAULT_COPTS}
  DEPS
    absl_bad_any_cast
    absl_config
    absl_core_headers
    absl_type_traits
    absl_utility
  PUBLIC
)

absl_cc_library(
  NAME
    bad_any_cast
  HDRS
   "bad_any_cast.h"
  COPTS
    ${ABSL_DEFAULT_COPTS}
  DEPS
    absl_bad_any_cast_impl
    absl_config
  PUBLIC
)

absl_cc_library(
  NAME
    bad_any_cast_impl
  SRCS
   "bad_any_cast.h"
   "bad_any_cast.cc"
  COPTS
    ${ABSL_DEFAULT_COPTS}
    ${ABSL_EXCEPTIONS_FLAG}
  LINKOPTS
    ${ABSL_EXCEPTIONS_FLAG_LINKOPTS}
  DEPS
    absl_base
    absl_config
)

absl_cc_test(
  NAME
    any_test
  SRCS
    "any_test.cc"
  COPTS
    ${ABSL_TEST_COPTS}
    ${ABSL_EXCEPTIONS_FLAG}
  LINKOPTS
    ${ABSL_EXCEPTIONS_FLAG_LINKOPTS}
  DEPS
    absl_any
    absl_base
    absl_config
    absl_exception_testing
    absl_test_instance_tracker
    gmock_main
)

absl_cc_test(
  NAME
    any_test_noexceptions
  SRCS
    "any_test.cc"
  COPTS
    ${ABSL_TEST_COPTS}
  DEPS
    absl_any
    absl_base
    absl_config
    absl_exception_testing
    absl_test_instance_tracker
    gmock_main
)

absl_cc_test(
  NAME
    any_exception_safety_test
  SRCS
    "any_exception_safety_test.cc"
  COPTS
    ${ABSL_TEST_COPTS}
    ${ABSL_EXCEPTIONS_FLAG}
  LINKOPTS
    ${ABSL_EXCEPTIONS_FLAG_LINKOPTS}
  DEPS
    absl_any
    absl_exception_safety_testing
    gmock_main
)

absl_cc_library(
  NAME
    span
  HDRS
    "span.h"
  SRCS
    "internal/span.h"
  COPTS
    ${ABSL_DEFAULT_COPTS}
  DEPS
    absl_algorithm
    absl_core_headers
    absl_throw_delegate
    absl_type_traits
  PUBLIC
)

absl_cc_test(
  NAME
    span_test
  SRCS
    "span_test.cc"
  COPTS
    ${ABSL_TEST_COPTS}
    ${ABSL_EXCEPTIONS_FLAG}
  LINKOPTS
    ${ABSL_EXCEPTIONS_FLAG_LINKOPTS}
  DEPS
    absl_span
    absl_base
    absl_config
    absl_core_headers
    absl_exception_testing
    absl_fixed_array
    absl_inlined_vector
    absl_hash_testing
    absl_strings
    gmock_main
)

absl_cc_test(
  NAME
    span_test_noexceptions
  SRCS
    "span_test.cc"
  COPTS
    ${ABSL_TEST_COPTS}
  DEPS
    absl_span
    absl_base
    absl_config
    absl_core_headers
    absl_exception_testing
    absl_fixed_array
    absl_inlined_vector
    absl_hash_testing
    absl_strings
    gmock_main
)

absl_cc_library(
  NAME
    optional
  HDRS
    "optional.h"
  SRCS
    "internal/optional.h"
  COPTS
    ${ABSL_DEFAULT_COPTS}
  DEPS
    absl_bad_optional_access
    absl_base_internal
    absl_config
    absl_core_headers
    absl_memory
    absl_type_traits
    absl_utility
  PUBLIC
)

absl_cc_library(
  NAME
    bad_optional_access
  HDRS
    "bad_optional_access.h"
  SRCS
    "bad_optional_access.cc"
  COPTS
    ${ABSL_DEFAULT_COPTS}
    ${ABSL_EXCEPTIONS_FLAG}
  LINKOPTS
    ${ABSL_EXCEPTIONS_FLAG_LINKOPTS}
  DEPS
    absl_base
    absl_config
  PUBLIC
)

absl_cc_library(
  NAME
    bad_variant_access
  HDRS
    "bad_variant_access.h"
  SRCS
    "bad_variant_access.cc"
  COPTS
    ${ABSL_DEFAULT_COPTS}
    ${ABSL_EXCEPTIONS_FLAG}
  LINKOPTS
    ${ABSL_EXCEPTIONS_FLAG_LINKOPTS}
  DEPS
    absl_base
    absl_config
  PUBLIC
)

absl_cc_test(
  NAME
    optional_test
  SRCS
    "optional_test.cc"
  COPTS
    ${ABSL_TEST_COPTS}
    ${ABSL_EXCEPTIONS_FLAG}
  LINKOPTS
    ${ABSL_EXCEPTIONS_FLAG_LINKOPTS}
  DEPS
    absl_optional
    absl_base
    absl_config
    absl_type_traits
    absl_strings
    gmock_main
)

absl_cc_test(
  NAME
    optional_exception_safety_test
  SRCS
    "optional_exception_safety_test.cc"
  COPTS
    ${ABSL_TEST_COPTS}
    ${ABSL_EXCEPTIONS_FLAG}
  LINKOPTS
    ${ABSL_EXCEPTIONS_FLAG_LINKOPTS}
  DEPS
    absl_optional
    absl_exception_safety_testing
    gmock_main
)

absl_cc_library(
  NAME
    variant
  HDRS
    "variant.h"
  SRCS
    "internal/variant.h"
  COPTS
    ${ABSL_DEFAULT_COPTS}
  DEPS
    absl_bad_variant_access
    absl_base_internal
    absl_config
    absl_core_headers
    absl_type_traits
    absl_utility
  PUBLIC
)

absl_cc_test(
  NAME
    variant_test
  SRCS
    "variant_test.cc"
  COPTS
    ${ABSL_TEST_COPTS}
    ${ABSL_EXCEPTIONS_FLAG}
  LINKOPTS
    ${ABSL_EXCEPTIONS_FLAG_LINKOPTS}
  DEPS
    absl_variant
    absl_config
    absl_core_headers
    absl_memory
    absl_type_traits
    absl_strings
    gmock_main
)

absl_cc_library(
  NAME
    compare
  HDRS
    "compare.h"
  COPTS
    ${ABSL_DEFAULT_COPTS}
  DEPS
    absl_core_headers
    absl_type_traits
  PUBLIC
)

absl_cc_test(
  NAME
    compare_test
  SRCS
    "compare_test.cc"
  COPTS
    ${ABSL_TEST_COPTS}
  DEPS
    absl_base
    absl_compare
    gmock_main
)

# TODO(cohenjon,zhangxy) Figure out why this test is failing on gcc 4.8
if(CMAKE_CXX_COMPILER_ID STREQUAL "GNU" AND CMAKE_CXX_COMPILER_VERSION VERSION_LESS 4.9)
else()
absl_cc_test(
  NAME
    variant_exception_safety_test
  SRCS
    "variant_exception_safety_test.cc"
  COPTS
    ${ABSL_TEST_COPTS}
    ${ABSL_EXCEPTIONS_FLAG}
  LINKOPTS
    ${ABSL_EXCEPTIONS_FLAG_LINKOPTS}
  DEPS
    absl_variant
    absl_config
    absl_exception_safety_testing
    absl_memory
    gmock_main
)
endif()
