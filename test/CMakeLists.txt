#
# Copyright Troy D. Straszheim
#
# Distributed under the Boost Software License, Version 1.0.
# See http://www.boost.org/LICENSE_1_0.txt
#
add_definitions(-DBOOST_TEST_NO_AUTO_LINK=1)
# shared needs:
add_definitions(-DBOOST_TEST_DYN_LINK=1)

if(BORLAND)
  add_definitions(-w-8080)
endif(BORLAND)

# Basic tests
ryppl_test_run(class_properties_test DEPENDS boost_unit_test_framework SHARED)
ryppl_test_run(basic_cstring_test DEPENDS boost_unit_test_framework-static)

# Program execution monitor tests
ryppl_test_run_fail(prg_exec_fail1 DEPENDS boost_prg_exec_monitor)
ryppl_test_run_fail(prg_exec_fail2 DEPENDS boost_prg_exec_monitor-static)
ryppl_test_run_fail(prg_exec_fail3 DEPENDS boost_prg_exec_monitor-static)
ryppl_test_run_fail(prg_exec_fail4 DEPENDS boost_prg_exec_monitor-static)

# Unit test framework tests
# NOTE: skipped errors_handling_test until I figure out what BBv2 is doing
ryppl_test_run(online_test)
ryppl_test_run_fail(minimal_test)
ryppl_test_run(foreach_test)
ryppl_test_run(output_test_stream_test DEPENDS boost_unit_test_framework SHARED)

# NOTE: skipped result_report_test until I figure out what BBv2 is doing

ryppl_test_run(parameterized_test_test DEPENDS boost_unit_test_framework SHARED)
ryppl_test_run(test_fp_comparisons DEPENDS boost_unit_test_framework SHARED)

# NOTE: skipped test_tools_test until I figure out what BBv2 is doing

ryppl_test_run(test_case_template_test DEPENDS boost_unit_test_framework SHARED)

ryppl_test_run(custom_exception_test DEPENDS boost_unit_test_framework-static)

ryppl_test_run(fixed_mapping_test DEPENDS boost_unit_test_framework SHARED)

# NOTE: skipped ifstream_line_iterator_test until I figure out what BBv2 is doing

ryppl_test_run(algorithms_test DEPENDS boost_unit_test_framework-static)
ryppl_test_run(token_iterator_test DEPENDS boost_unit_test_framework SHARED)
ryppl_test_run(boost_check_equal_str DEPENDS boost_unit_test_framework SHARED)
