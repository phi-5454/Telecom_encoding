# BASED ON https://github.com/albertchan/cmake-c-template/blob/master/CMakeLists.txt
cmake_minimum_required(VERSION 3.15)

# Definitions
set(PROJECT_NAME telecom_encoding)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/bin")

project(${PROJECT_NAME})
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=c17")


# Enable strict warnings and -pedantic for all targets
add_compile_options(
    -Wall                  # Enable most common warnings
    -Wextra                # Enable extra warnings
    -Werror                # Treat warnings as errors
    -Wpedantic             # Enable pedantic warnings
    -Wshadow               # Warn about variable shadowing
    -Wformat=2             # Enable additional format string checks
    -Wno-unused-parameter  # Disable warning for unused parameters
    -Wpedantic 
    -Waggregate-return
    -Wbad-function-cast
    -Wcast-align
    -Wcast-qual
    -Wdeclaration-after-statement
    -Wfloat-equal
    -Wlogical-op
    -Wmissing-declarations
    -Wmissing-include-dirs
    -Wmissing-prototypes
    -Wnested-externs
    -Wpointer-arith
    -Wredundant-decls
    -Wsequence-point
    -Wstrict-prototypes
    -Wswitch
    -Wundef
    -Wunreachable-code
    -Wunused-but-set-parameter
    -Wwrite-strings
)

# Include paths
set(INCLUDE_DIRS ${INCLUDE_DIRS} ${PROJECT_SOURCE_DIR}/include)

# Assign the include directories
include_directories(${INCLUDE_DIRS})

# Find library sources
#file(GLOB_RECURSE LIB_SRC_FILES include/*/*.c)

# Build static/shared library
#add_library(${PROJECT_NAME}_LIB STATIC ${LIB_SRC_FILES})

# Install library
#install(TARGETS ${PROJECT_NAME}_LIB DESTINATION lib)

# Install library headers
#file(GLOB_RECURSE LIB_INC_FILES include/*/*.h)
#install(FILES ${LIB_INC_FILES} DESTINATION include)

set(SOURCE_FILES src/main.c)
add_executable(telecom_encoding ${SOURCE_FILES})
#target_link_libraries(${PROJECT_NAME} ${PROJECT_NAME}_LIB)
