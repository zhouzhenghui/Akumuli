include_directories(../include)
include_directories(../src)
add_executable(
    ut_main
        test_sequencer.cpp
        test_page.cpp
        test_mmap.cpp
        test_sorting.cpp
        test_cursor.cpp
        test_compression.cpp
        ../src/storage.cpp
        ../src/page.cpp
        ../src/akumuli.cpp
        ../src/util.cpp
        ../src/sequencer.cpp
        ../src/cursor.cpp
)
target_link_libraries(
    ut_main
    "${APR_LIBRARY}"
    ${Boost_LIBRARIES}
    libboost_coroutine.a
    libboost_context.a
    pthread
)
add_test(akumuli_tests ut_main)
