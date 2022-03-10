cmake_minimum_required(VERSION 3.11)

project(Assimp-FBXLoader)

file(GLOB_RECURSE ASSIMP_FBXLOADER_SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/code/*.cpp)

add_subdirectory(thirdparty/zlib)

add_library(assimp-fbxloader STATIC ${ASSIMP_FBXLOADER_SOURCES})
target_include_directories(assimp-fbxloader
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include/
    ${CMAKE_CURRENT_SOURCE_DIR}/code/
    ${CMAKE_CURRENT_SOURCE_DIR}/
    $<TARGET_FILE_DIR:zlib>
    thirdparty/zlib
)
target_link_libraries(assimp-fbxloader zlibstatic)
