cmake_minimum_required(VERSION 4.0)
project(unordered_dense VERSION 5.0.1 LANGUAGES CXX)

add_library(unordered_dense INTERFACE)
add_library(unordered_dense::unordered_dense ALIAS unordered_dense)
set_target_properties(unordered_dense PROPERTIES VERSION "${PROJECT_VERSION}")
target_compile_features(unordered_dense INTERFACE cxx_std_17)
target_include_directories(unordered_dense INTERFACE
    "${CMAKE_CURRENT_SOURCE_DIR}/include"
)

option(UNORDERED_DENSE_INSTALL "Enable installation for unordered_dense." OFF)
if(UNORDERED_DENSE_INSTALL)
    include(GNUInstallDirs)
    install(
        DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/include/"
        DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}"
    )
endif()
