cmake_minimum_required(VERSION 3.10)

unset(ENV{TVOS_DEPLOYMENT_TARGET})
unset(ENV{CODE_SIGN_IDENTITY})

option(HUNTER_STATUS_DEBUG "Debug info" ON)

include("${CMAKE_CURRENT_LIST_DIR}/../../../../cmake/HunterGate.cmake")

HunterGate(
    URL "${HUNTER_HOST_URL}"
    SHA1 "${HUNTER_HOST_SHA1}"
)

project(ICUHost)

#
## Print all env variables out.
# execute_process(COMMAND "${CMAKE_COMMAND}" "-E" "environment")
#
## Print all CMAKE variables out
# get_cmake_property(_variableNames VARIABLES)
# list (SORT _variableNames)
# foreach (_variableName ${_variableNames})
#     message(STATUS "All-Cmake-Variables-For-Debugging    ${_variableName}=${${_variableName}}")
# endforeach()

hunter_add_package(ICU)
