cmake_minimum_required (VERSION 2.8.10...3.20)

project (Libpll)

if(NOT DEFINED binarytreesummation_version)
    set(binarytreesummation_version main)
endif()
include(FetchContent)

if(DEFINED REPRODUCIBLE)
    #FetchContent_MakeAvailable(reprored)
add_definitions(-DREPRODUCIBLE)
endif()

add_subdirectory(src)

set(PLL_EXPORTED_INCLUDE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/src PARENT_SCOPE)
