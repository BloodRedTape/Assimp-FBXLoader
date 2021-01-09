cmake_minimum_required(VERSION 3.11)

project(Assimp-FBXLoader)

file(GLOB_RECURSE ASSIMP_FBXLOADER_SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/code/*.cpp)

add_library(assimp-fbxloader STATIC ${ASSIMP_FBXLOADER_SOURCES})
target_include_directories(assimp-fbxloader PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/include/
    ${CMAKE_CURRENT_SOURCE_DIR}/code/
    ${CMAKE_CURRENT_SOURCE_DIR}/
)
target_link_libraries(assimp-fbxloader z)
