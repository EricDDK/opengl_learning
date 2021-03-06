cmake_minimum_required (VERSION 3.4)
list(APPEND CMAKE_CXX_FLAGS "-std=c++11")
project (OpenGLLearning)
find_package(OpenGL REQUIRED)

include_directories("./build")
include_directories("./include")
LINK_DIRECTORIES("./libs")

if(WIN32)
  set(LIBS glfw3 opengl32 assimp)
elseif(UNIX AND NOT APPLE)
  set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -Wall")
  find_package(OpenGL REQUIRED)
  add_definitions(${OPENGL_DEFINITIONS})
  find_package(X11 REQUIRED)
  set(LIBS ${GLFW3_LIBRARY} X11 Xrandr Xinerama Xi Xxf86vm Xcursor GL dl pthread ${ASSIMP_LIBRARY})
  set (CMAKE_CXX_LINK_EXECUTABLE "${CMAKE_CXX_LINK_EXECUTABLE} -ldl")
elseif(APPLE)
  INCLUDE_DIRECTORIES(/System/Library/Frameworks)
  FIND_LIBRARY(COCOA_LIBRARY Cocoa)
  FIND_LIBRARY(OpenGL_LIBRARY OpenGL)
  FIND_LIBRARY(IOKit_LIBRARY IOKit)
  FIND_LIBRARY(CoreVideo_LIBRARY CoreVideo)
  MARK_AS_ADVANCED(COCOA_LIBRARY OpenGL_LIBRARY)
  SET(APPLE_LIBS ${COCOA_LIBRARY} ${IOKit_LIBRARY} ${OpenGL_LIBRARY} ${CoreVideo_LIBRARY})
  SET(APPLE_LIBS ${APPLE_LIBS} ${GLFW3_LIBRARY} ${ASSIMP_LIBRARY})
  set(LIBS glfw3 ${LIBS} ${APPLE_LIBS})
else()
  set(LIBS )
endif(WIN32)

#####################################           1           ########################################################

add_executable(
    main_1_1
    project/1.1_hello_windows/main.cpp
    project/glad.c
)
target_link_libraries(main_1_1 ${LIBS})

add_executable(
    main_1_2_1
    project/1.2_hello_triangle/main.cpp
    project/glad.c
)
target_link_libraries(main_1_2_1 ${LIBS})
add_executable(
    main_1_2_2
    project/1.2_hello_triangle/main_2.cpp
    project/glad.c
)
target_link_libraries(main_1_2_2 ${LIBS})

add_executable(
    main_1_3
    project/1.3_shader/main.cpp
    project/glad.c
)
target_link_libraries(main_1_3 ${LIBS})
add_executable(
    main_1_3_2
    project/1.3_shader/main_2.cpp
    project/glad.c
)
target_link_libraries(main_1_3_2 ${LIBS})
add_executable(
    main_1_3_3
    project/1.3_shader/main_3.cpp
    project/glad.c
)
target_link_libraries(main_1_3_3 ${LIBS})

add_executable(
    main_1_4
    project/1.4_texture/main.cpp
    project/glad.c
)
target_link_libraries(main_1_4 ${LIBS})
add_executable(
    main_1_4_2
    project/1.4_texture/main_2.cpp
    project/glad.c
)
target_link_libraries(main_1_4_2 ${LIBS})

add_executable(
    main_1_5
    project/1.5_transformations/main.cpp
    project/glad.c
)
target_link_libraries(main_1_5 ${LIBS})

add_executable(
    main_1_6
    project/1.6_coordinate_system/main.cpp
    project/glad.c
)
target_link_libraries(main_1_6 ${LIBS})
add_executable(
    main_1_6_2
    project/1.6_coordinate_system/main_2.cpp
    project/glad.c
)
target_link_libraries(main_1_6_2 ${LIBS})
add_executable(
    main_1_6_3
    project/1.6_coordinate_system/main_3.cpp
    project/glad.c
)
target_link_libraries(main_1_6_3 ${LIBS})

add_executable(
    main_1_7
    project/1.7_camera/main.cpp
    project/glad.c
)
target_link_libraries(main_1_7 ${LIBS})
add_executable(
    main_1_7_2
    project/1.7_camera/main_2.cpp
    project/glad.c
)
target_link_libraries(main_1_7_2 ${LIBS})
add_executable(
    main_1_7_3
    project/1.7_camera/main_3.cpp
    project/glad.c
)
target_link_libraries(main_1_7_3 ${LIBS})
add_executable(
    main_1_7_4
    project/1.7_camera/main_4.cpp
    project/glad.c
)
target_link_libraries(main_1_7_4 ${LIBS})

#####################################           2           ########################################################

add_executable(
    main_2_1
    project/2.1_colors/main.cpp
    project/glad.c
)
target_link_libraries(main_2_1 ${LIBS})

add_executable(
    main_2_2
    project/2.2_basic_lighting/main.cpp
    project/glad.c
)
target_link_libraries(main_2_2 ${LIBS})
add_executable(
    main_2_2_2
    project/2.2_basic_lighting/main_2.cpp
    project/glad.c
)
target_link_libraries(main_2_2_2 ${LIBS})
add_executable(
    main_2_2_3
    project/2.2_basic_lighting/main_3.cpp
    project/glad.c
)
target_link_libraries(main_2_2_3 ${LIBS})

add_executable(
    main_2_3
    project/2.3_Materials/main.cpp
    project/glad.c
)
target_link_libraries(main_2_3 ${LIBS})

add_executable(
    main_2_4
    project/2.4_lighting_maps/main.cpp
    project/glad.c
)
target_link_libraries(main_2_4 ${LIBS})
add_executable(
    main_2_4_2
    project/2.4_lighting_maps/main_2.cpp
    project/glad.c
)
target_link_libraries(main_2_4_2 ${LIBS})

add_executable(
    main_2_5
    project/2.5_light_casters/main.cpp
    project/glad.c
)
target_link_libraries(main_2_5 ${LIBS})
add_executable(
    main_2_5_2
    project/2.5_light_casters/main_2.cpp
    project/glad.c
)
target_link_libraries(main_2_5_2 ${LIBS})
add_executable(
    main_2_5_3
    project/2.5_light_casters/main_3.cpp
    project/glad.c
)
target_link_libraries(main_2_5_3 ${LIBS})
add_executable(
    main_2_5_4
    project/2.5_light_casters/main_4.cpp
    project/glad.c
)
target_link_libraries(main_2_5_4 ${LIBS})

add_executable(
    main_2_6
    project/2.6_multiple_lights/main.cpp
    project/glad.c
)
target_link_libraries(main_2_6 ${LIBS})

#####################################           3           ########################################################

add_executable(
    main_3_1
    project/3.1_assimp/main.cpp
    project/glad.c
)
target_link_libraries(main_3_1 ${LIBS})

#####################################           4           ########################################################

add_executable(
    main_4_1
    project/4.1_depth_testing/main.cpp
    project/glad.c
)
target_link_libraries(main_4_1 ${LIBS})
add_executable(
    main_4_1_2
    project/4.1_depth_testing/main_2.cpp
    project/glad.c
)
target_link_libraries(main_4_1_2 ${LIBS})

add_executable(
    main_4_2
    project/4.2_stencil_testing/main.cpp
    project/glad.c
)
target_link_libraries(main_4_2 ${LIBS})

add_executable(
    main_4_3
    project/4.3_blend/main.cpp
    project/glad.c
)
target_link_libraries(main_4_3 ${LIBS})
add_executable(
    main_4_3_2
    project/4.3_blend/main_2.cpp
    project/glad.c
)
target_link_libraries(main_4_3_2 ${LIBS})

add_executable(
    main_4_5
    project/4.5_frame_buffer/main.cpp
    project/glad.c
)
target_link_libraries(main_4_5 ${LIBS})

add_executable(
    main_4_6_1
    project/4.6_cubemaps/main.cpp
    project/glad.c
)
target_link_libraries(main_4_6_1 ${LIBS})
add_executable(
    main_4_6_2
    project/4.6_cubemaps/main_2.cpp
    project/glad.c
)
target_link_libraries(main_4_6_2 ${LIBS})

add_executable(
    main_4_8_1
    project/4.8_advanced_glsl/main.cpp
    project/glad.c
)
target_link_libraries(main_4_8_1 ${LIBS})

add_executable(
    main_4_9_1
    project/4.9_geometry_shader/main.cpp
    project/glad.c
)
target_link_libraries(main_4_9_1 ${LIBS})
add_executable(
    main_4_9_2
    project/4.9_geometry_shader/main_2.cpp
    project/glad.c
)
target_link_libraries(main_4_9_2 ${LIBS})

add_executable(
    main_4_10_1
    project/4.10_instancing/main.cpp
    project/glad.c
)
target_link_libraries(main_4_10_1 ${LIBS})
add_executable(
    main_4_10_2
    project/4.10_instancing/main_2.cpp
    project/glad.c
)
target_link_libraries(main_4_10_2 ${LIBS})

add_executable(
    main_4_11
    project/4.11_anti_aliasing/main.cpp
    project/glad.c
)
target_link_libraries(main_4_11 ${LIBS})

#####################################           5           ########################################################

add_executable(
    main_5_1
    project/5.1_advanced_lighting/main.cpp
    project/glad.c
)
target_link_libraries(main_5_1 ${LIBS})

add_executable(
    main_5_2
    project/5.2_gamma_correction/main.cpp
    project/glad.c
)
target_link_libraries(main_5_2 ${LIBS})

add_executable(
    main_5_3_1
    project/5.3_shadow_mapping/main.cpp
    project/glad.c
)
target_link_libraries(main_5_3_1 ${LIBS})
add_executable(
    main_5_3_1_2
    project/5.3_shadow_mapping/main_2.cpp
    project/glad.c
)
target_link_libraries(main_5_3_1_2 ${LIBS})

add_executable(
    main_5_5
    project/5.5_normal_mapping/main.cpp
    project/glad.c
)
target_link_libraries(main_5_5 ${LIBS})

add_executable(
    main_5_7
    project/5.7_HDR/main.cpp
    project/glad.c
)
target_link_libraries(main_5_7 ${LIBS})

add_executable(
    main_5_8
    project/5.8_bloom/main.cpp
    project/glad.c
)
target_link_libraries(main_5_8 ${LIBS})

add_executable(
    main_5_9_1
    project/5.9_deffered_shading/main.cpp
    project/glad.c
)
target_link_libraries(main_5_9_1 ${LIBS})
