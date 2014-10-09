# (c) SRON - Netherlands Institute for Space Research (2014).
# All Rights Reserved.
# This software is distributed under the BSD 2-clause license.

## =============================================================================
##
##  CMake projects settings
##
## =============================================================================


# Name of the project
project (ocalfw_extras)

# Minimum required version of CMake
cmake_minimum_required (VERSION 2.8.2)

set (PROJECT_VERSION_MAJOR "0")
set (PROJECT_VERSION_MINOR "1")
set (PROJECT_VERSION_PATCH "0")
set (PROJECT_VERSION_SERIES "${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}")
set (PROJECT_VERSION        "${PROJECT_VERSION_SERIES}.${PROJECT_VERSION_PATCH}")

## =============================================================================
##
##  Configuration options
##
## =============================================================================

option (WITH_TESTS "Enable the CTest test driver and build test programs?"   TRUE )
option (TIMEOUT_UNIT_TEST     "Timeout for unit tests"                       300  )
option (TIMEOUT_EXTENDED_TEST "Timeout for extended tests (e.g. processing)" 1200 )

##__________________________________________________________
## Handle option: Enable test driver and build test programs?

if (WITH_TESTS)
    ## Control parameters for running the tests
    set (DART_TESTING_TIMEOUT "1200" CACHE STRING "Maximum time allowed before CTest will kill the test" FORCE)
    # Include test driver and enable it
    include (CTest)
    enable_testing()
endif (WITH_TESTS)

## =============================================================================
##
##  Build instructions
##
## =============================================================================

add_subdirectory (scripts)

## =============================================================================
##
##  Configuration summary
##
## =============================================================================

message ("o---------------------------------------------------------o"     )
message (" [ Project configuration ]"                                      )
message ("  .. Project name ................. = ${PROJECT_NAME}"           )
message ("  .. Project version .............. = ${PROJECT_VERSION}"        )
message (" --------------------------------------------------------- "     )
message (" [ System configuration ]"                                       )
message ("  .. System ....................... = ${CMAKE_SYSTEM}"           )
message ("  .. Processor type ............... = ${CMAKE_SYSTEM_PROCESSOR}" )
message ("  .. CMake executable ............. = ${CMAKE_COMMAND}"          )
message ("  .. CMake version ................ = ${CMAKE_VERSION}"          )
message ("  .. Extra search prefix .......... = ${CMAKE_SEARCH_PREFIX}"    )
message ("  .. Installation prefix .......... = ${CMAKE_INSTALL_PREFIX}"   )
message ("o---------------------------------------------------------o"     )
