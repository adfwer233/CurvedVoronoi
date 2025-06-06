cmake_minimum_required(VERSION 3.26)

project(CurvedVoronoi VERSION 1.0 DESCRIPTION "CurvedVoronoi Demo" LANGUAGES CXX)

find_package(Vulkan REQUIRED)
find_package(OpenMP REQUIRED)

add_subdirectory(GraphicsLab)

set(CMAKE_CXX_STANDARD 20)

set(SRC_FILE main.cpp project.cpp)

add_executable(${PROJECT_NAME} ${SRC_FILE})

add_definitions(-DDATA_DIR="${CMAKE_CURRENT_SOURCE_DIR}/GraphicsLab/data")

get_target_property(GraphicsLabIncludes GraphicsLabLib INCLUDE_DIRECTORIES)

target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_SOURCE_DIR}/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${GraphicsLabIncludes})
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_SOURCE_DIR}/GraphicsLab/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${VK_SDK_INCLUDE})

target_link_libraries(${PROJECT_NAME} PUBLIC GraphicsLab_Lib)

add_custom_command(
        TARGET ${PROJECT_NAME} POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy_directory "${CMAKE_CURRENT_SOURCE_DIR}/GraphicsLab/configs" $<TARGET_FILE_DIR:${PROJECT_NAME}>
)

add_custom_command(TARGET ${PROJECT_NAME}  POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E make_directory $<TARGET_FILE_DIR:${PROJECT_NAME}>/font
)

add_custom_command(
        TARGET ${PROJECT_NAME} POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy_directory "${CMAKE_CURRENT_SOURCE_DIR}/GraphicsLab/assets/font" $<TARGET_FILE_DIR:${PROJECT_NAME}>/font
)

add_custom_command(
        TARGET ${PROJECT_NAME} POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy_directory "${CMAKE_CURRENT_SOURCE_DIR}/GraphicsLab/shader" $<TARGET_FILE_DIR:${PROJECT_NAME}>/shader
)

add_custom_command(
        TARGET ${PROJECT_NAME} POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy_directory "${CMAKE_CURRENT_SOURCE_DIR}/shader" $<TARGET_FILE_DIR:${PROJECT_NAME}>/custom_shader
)

add_subdirectory(shader)
add_dependencies(${PROJECT_NAME} ${PROJECT_NAME}_shaders)
