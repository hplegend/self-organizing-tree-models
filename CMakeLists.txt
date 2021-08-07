cmake_minimum_required(VERSION 3.11)

project(self-organizing-tree-models)

set(DCMAKE_SH="CMAKE_SH-NOTFOUND")

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_EXPORT_COMPILE_COMMANDS 1)

add_definitions(-Wall)
add_definitions(-Wextra)

if(CMAKE_BUILD_TYPE MATCHES "Debug")
  add_definitions(-DDEBUGGING)
endif()

set(TARGET_INCLUDE
        "D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\include"
        "D:\\\\hplegend\\\\Opencv4\\\\opencv\\\\build\\\\include"
        "D:\\\\hplegend\\\\codes\\\\graphic-pkg\\\\glfw-3.3.1\\\\include"
        "D:\\\\hplegend\\\\codes\\\\graphic-pkg\\\\glm-0.9.9.8\\\\glm"
        )

include_directories(self-organizing-tree-models ${TARGET_INCLUDE})

include_directories(glad/include)

add_executable(self-organizing-tree-models
               glad/src/glad.c
               src/Application.cpp
               src/BoundingBox.cpp
               src/BoundingBox.hpp
               src/Random.cpp
               src/Random.hpp
               src/Point.cpp
               src/Point.hpp
               src/Tree.cpp
               src/Tree.hpp
               src/Environment.cpp
               src/Environment.hpp
               src/OpenGlWindow.cpp
               src/OpenGlWindow.hpp
               src/Metamer.cpp
               src/Metamer.hpp
               src/Vertex.hpp
               src/Image.cpp
               src/Image.hpp
               src/MarkerSet.cpp
               src/MarkerSet.hpp
               src/Color.hpp
               src/Range.cpp
               src/Range.hpp
               src/Types.hpp
               src/Text.cpp
               src/Text.hpp
               src/Vector.cpp
               src/Vector.hpp
               src/SpaceAnalysis.hpp
               src/PointAverage.cpp
               src/PointAverage.hpp
               src/MarkerSetRanges.hpp
               src/Marker.cpp
               src/Marker.hpp
               src/UserAction.hpp)

# find 系列需要在运行时编译，因此直接指定lib

set(TARGET_LIBS
        #"D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\libglaux.a"
        "D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\libopengl32.a"
        #"D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\libglaux.a"
        "D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\libglu32.a"
        "D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\libkernel32.a"
        "D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\glut32.lib"
        "D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\libglfw3.a"
        "D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\libglfw3dll.a"
        "D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\glew32.lib"
        "D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\glew32mx.lib"
        "D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\glew32mxs.lib"
        "D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\glew32s.lib"
        "D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\glut.lib"
        "D:\\\\Program Files\\\\CodeBlocks\\\\MinGW\\\\x86_64-w64-mingw32\\\\lib\\\\AntTweakBar.lib"
        "D:\\\\hplegend\\\\Opencv4\\\\cmakelib\\\\libopencv_core412.dll.a"
        "D:\\\\hplegend\\\\Opencv4\\\\cmakelib\\\\libopencv_highgui412.dll.a"
        "D:\\\\hplegend\\\\Opencv4\\\\cmakelib\\\\libopencv_imgproc412.dll.a"
        )

target_link_libraries(self-organizing-tree-models ${TARGET_LIBS})
