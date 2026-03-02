cmake_minimum_required(VERSION 3.5)
project(calculator C)

add_subdirectory(include)
add_subdirectory(src)

include_directories(include)

enable_testing()

add_test(NAME t1 COMMAND $<TARGET_FILE:calculator> add 2 3)
add_test(NAME t2 COMMAND $<TARGET_FILE:calculator> sub 3 -2)
add_test(NAME t3 COMMAND $<TARGET_FILE:calculator> mul 5 5)
add_test(NAME t4 COMMAND $<TARGET_FILE:calculator> div 1 5)

add_test(NAME t5 COMMAND $<TARGET_FILE:calculator> car 5)

set_tests_properties(t1 PROPERTIES PASS_REGULAR_EXPRESSION "5\\.000000")
set_tests_properties(t2 PROPERTIES PASS_REGULAR_EXPRESSION "5\\.000000")
set_tests_properties(t3 PROPERTIES PASS_REGULAR_EXPRESSION "25\\.000000")
set_tests_properties(t4 PROPERTIES PASS_REGULAR_EXPRESSION "0\\.200000")
set_tests_properties(t5 PROPERTIES PASS_REGULAR_EXPRESSION "25\\.000000")
