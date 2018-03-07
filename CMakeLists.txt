cmake_minimum_required(VERSION 3.9)

project(OpenBSP_MinGW)

set(CMAKE_CXX_STANDARD 11)

find_package(PkgConfig)

pkg_check_modules(FREETYPE freetype2 REQUIRED)
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)
pkg_check_modules(GLEW glew REQUIRED)

find_package(glm REQUIRED)


include_directories(${FREETYPE_INCLUDE_DIRS})
include_directories(${GLEW_INCLUDE_DIRS})
include_directories(${GLM_INCLUDE_DIRS})

add_executable(OpenBSP_MinGW
        Atlas.cpp
        Atlas.h
        Bsp.cpp
        Bsp.h
        BspDef.h
        BspRenderer.cpp
        BspRenderer.h
        Camera.cpp
        Camera.h
        Color.cpp
        Color.h
        Engine.cpp
        Engine.h
        Entity.cpp
        Entity.h
        Font.cpp
        Font.h
        Image.cpp
        Image.h
        LightMap.cpp
        LightMap.h
        Main.cpp
        Main.h
        Rect.h
        Shader.cpp
        Shader.h
        ShaderManager.cpp
        ShaderManager.h
        SharedDefs.h
        TextRenderer.cpp
        TextRenderer.h
        Texture.cpp
        Texture.h
        Utils.h)

target_link_libraries(OpenBSP_MinGW ${FREETYPE_LIBRARIES})
target_link_libraries(OpenBSP_MinGW ${OPENGL_LIBRARIES})
target_link_libraries(OpenBSP_MinGW glfw)
target_link_libraries(OpenBSP_MinGW ${GLEW_LIBRARIES})

message(XX ${GLFW_LIBRARIES})