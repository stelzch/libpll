cmake_minimum_required (VERSION 2.8.10...3.20)

project (Libpll)

if(NOT DEFINED binarytreesummation_version)
    set(binarytreesummation_version main)
endif()
include(FetchContent)

if(DEFINED REPORDUCIBLE)
FetchContent_Declare(
        binarytreesummation
        GIT_REPOSITORY https://git.ch-st.de/christoph/binary_tree_summation.git
        GIT_TAG ${binarytreesummation_version}
)
FetchContent_MakeAvailable(binarytreesummation)
endif()

add_subdirectory(src)

set(PLL_EXPORTED_INCLUDE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/src PARENT_SCOPE)
