#Generated by VisualGDB project wizard.
#Note: VisualGDB will automatically update this file when you add new sources to the project.

cmake_minimum_required(VERSION 2.7)
project(CMakeDebugger)

function(set_version_from_file target)
	file(READ "version.txt" VERSION_FROM_FILE)

	if (${VERSION_FROM_FILE} LESS "2")
		message(FATAL_ERROR "Invalid version")
	endif()

	target_compile_definitions(${target} PRIVATE PROJECT_VERSION=${VERSION_FROM_FILE})
endfunction()

set(LIBRARIES_FROM_REFERENCES "")
add_executable(CMakeDebugger CMakeDebugger.cpp)
set_version_from_file(CMakeDebugger)

target_link_libraries(CMakeDebugger "${LIBRARIES_FROM_REFERENCES}")
