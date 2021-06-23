project(recoup)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")

cmake_minimum_required (VERSION 3.16)

add_library(recoup STATIC ../recoup.c)

enable_testing()
add_subdirectory(test)

if(CJSON_COVERAGE)
    message("adding coverage ${CJSON_COVERAGE}")
    if(CMAKE_BUILD_TYPE MATCHES Debug)
        set_target_properties(storage PROPERTIES COMPILE_FLAGS "${CMAKE_C_FLAGS} -fprofile-arcs -ftest-coverage -Wall -pedantic -Wextra")
        set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -fprofile-arcs -ftest-coverage ")
        include(CodeCoverage)
        setup_target_for_coverage(
            NAME coverage
            EXECUTABLE build/recoup_test)
    endif()
endif()
