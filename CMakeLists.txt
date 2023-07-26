cmake_minimum_required(VERSION 3.9)
project(soil2 LANGUAGES CXX C VERSION 1.0.0)

add_library(soil2
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/image_DXT.c"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/image_helper.c"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/wfETC.c"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/common/common.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/libhelper.c"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/pkm_helper.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/pvr_helper.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/stb_image.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/stb_image_write.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/stbi_DDS.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/stbi_DDS_c.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/stbi_ext.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/stbi_ext_c.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/stbi_pkm.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/stbi_pkm_c.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/stbi_pvr.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/stbi_pvr_c.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/wfETC.h"
)

target_compile_options(soil2 PRIVATE
    $<$<CXX_COMPILER_ID:Clang>:-fPIC>
    $<$<CXX_COMPILER_ID:GNU>:-fPIC>
)

target_include_directories(soil2 PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/src/SOIL2/>
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/src/common/>
    $<INSTALL_INTERFACE:include>
)
