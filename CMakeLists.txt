cmake_minimum_required (VERSION 2.8.12) 
project (gl)

find_package(OpenGL)
if (OPENGL_FOUND)
  MESSAGE("OpenGL Correctly Found")
  include_directories(${OPENGL_INCLUDE_DIR})
else (OPENGL_FOUND)
  MESSAGE("OpenGL environment missing")
endif()


set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "fwrwere")
set(GLFW_BUILD_TESTS OFF CACHE BOOL "aegegherh")
set(GLFW_BUILD_DOCS OFF CACHE BOOL "aegegherh")
set(GLFW_INSTALL OFF CACHE BOOL "fasdfa")

add_subdirectory(ext/glfw)
include_directories(ext/glfw/include)

add_executable (gl src/main.cpp)

target_link_libraries (gl glfw ${GLFW_LIBRARIES} ${OPENGL_LIBRARIES})