foreach(testname logger_provider_sdk_test logger_sdk_test)
  add_executable(${testname} "${testname}.cc")
  target_link_libraries(${testname} ${GTEST_BOTH_LIBRARIES}
                        ${CMAKE_THREAD_LIBS_INIT} opentelemetry_logs)
  gtest_add_tests(TARGET ${testname} TEST_PREFIX logs. TEST_LIST ${testname})
endforeach()
