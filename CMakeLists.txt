cmake_minimum_required(VERSION 3.10)

project(all)

set(PRINT_VERSION_MAJOR 0)
set(PRINT_VERSION_MINOR 1)
set(PRINT_VERSION_PATCH 0)
set(PRINT_VERSION_TWEAK 0)
set(PRINT_VERSION
  ${PRINT_VERSION_MAJOR}.${PRINT_VERSION_MINOR}.${PRINT_VERSION_PATCH}.${PRINT_VERSION_TWEAK})
set(PRINT_VERSION_STRING "v${PRINT_VERSION}")


add_subdirectory(solver_application)
add_subdirectory(hello_world_application)

# file(GLOB_RECURSE HEADERS "${CMAKE_CURRENT_SOURCE_DIR}/*.h")
# message("HEADERS" ${HEADERS})
# install(FILES ${HEADERS} DESTINATION include)

# message("HEADERS" ${HEADERS})


install(TARGETS solver_app
    RUNTIME DESTINATION bin
)

# install(TARGETS formatter_ex
#     ARCHIVE DESTINATION lib
#     LIBRARY DESTINATION lib
#     RUNTIME DESTINATION bin
#     PUBLIC_HEADER DESTINATION include
# )


# install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include DESTINATION include)

# install(EXPORT solver-config DESTINATION cmake)
# install(EXPORT formatter-config DESTINATION cmake)
# install(EXPORT formatter_ex-config DESTINATION cmake)

#install(EXPORT print-config DESTINATION cmake)

include(CPackConfig.cmake)
