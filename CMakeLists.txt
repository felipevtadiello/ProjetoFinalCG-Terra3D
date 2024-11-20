cmake_minimum_required(VERSION 3.12)

project(ProjetoFinal)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Add o exe do projeto
add_executable(ProjetoFinal "main.cpp")

# Config do CMake para localizar GLM
set(GLM_INCLUDE_DIR "${CMAKE_SOURCE_DIR}/deps/glm")
target_include_directories(ProjetoFinal PRIVATE "${GLM_INCLUDE_DIR}")

# GLFW
set(GLFW_INCLUDE_DIR "${CMAKE_SOURCE_DIR}/deps/glfw/include")
set(GLFW_LIBRARY_DIR "${CMAKE_SOURCE_DIR}/deps/glfw/lib-vc2019")
target_include_directories(ProjetoFinal PRIVATE "${GLFW_INCLUDE_DIR}")
target_link_libraries(ProjetoFinal PRIVATE "${GLFW_LIBRARY_DIR}/glfw3.lib")

# GLEW
set(GLEW_INCLUDE_DIR "${CMAKE_SOURCE_DIR}/deps/glew/include")
set(GLEW_LIBRARY_DIR "${CMAKE_SOURCE_DIR}/deps/glew/lib/Release/x64")
target_include_directories(ProjetoFinal PRIVATE "${GLEW_INCLUDE_DIR}")

# Usa o caminho completo para glew32.lib
target_link_libraries(ProjetoFinal PRIVATE "${GLEW_LIBRARY_DIR}/glew32.lib")

# STB
set(STB_INCLUDE_DIR "${CMAKE_SOURCE_DIR}/deps/stb")
target_include_directories(ProjetoFinal PRIVATE "${STB_INCLUDE_DIR}")

# Assimp
set(ASSIMP_ROOT "${CMAKE_SOURCE_DIR}/deps/assimp")
set(ASSIMP_INCLUDE_DIR "${ASSIMP_ROOT}/include")
set(ASSIMP_LIBRARY_DIR "${ASSIMP_ROOT}/lib")
set(ASSIMP_DLL_DIR "${ASSIMP_ROOT}/bin")

if(EXISTS "${ASSIMP_INCLUDE_DIR}" AND EXISTS "${ASSIMP_LIBRARY_DIR}")
    message(STATUS "Assimp include directory: ${ASSIMP_INCLUDE_DIR}")
    message(STATUS "Assimp library directory: ${ASSIMP_LIBRARY_DIR}")
    target_include_directories(ProjetoFinal PRIVATE "${ASSIMP_INCLUDE_DIR}")
    target_link_libraries(ProjetoFinal PRIVATE "${ASSIMP_LIBRARY_DIR}/assimp-vc143-mt.lib")
else()
    message(FATAL_ERROR "Assimp não encontrado nos diretórios especificados: ${ASSIMP_INCLUDE_DIR} ou ${ASSIMP_LIBRARY_DIR}")
endif()

# Biblioteca OpenGL
target_link_libraries(ProjetoFinal PRIVATE opengl32.lib)

# Faz a copia das DLLs necessárias para o diretório de saída
add_custom_command(TARGET ProjetoFinal POST_BUILD
                   COMMAND ${CMAKE_COMMAND} -E copy
                   "${CMAKE_SOURCE_DIR}/deps/glew/bin/Release/x64/glew32.dll"
                   "$<TARGET_FILE_DIR:ProjetoFinal>/glew32.dll")
                   
add_custom_command(TARGET ProjetoFinal POST_BUILD
                   COMMAND ${CMAKE_COMMAND} -E copy
                   "C:/Program Files/Assimp/bin/x64/assimp-vc143-mt.dll"
                   "$<TARGET_FILE_DIR:ProjetoFinal>/assimp-vc143-mt.dll")