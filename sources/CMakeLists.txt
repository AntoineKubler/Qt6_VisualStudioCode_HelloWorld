cmake_minimum_required(VERSION 3.16)

set( CMAKE_C_COMPILER "F:/Qt/Tools/mingw1120_64/bin/gcc.exe" )
set( CMAKE_CXX_COMPILER "F:/Qt/Tools/mingw1120_64/bin/g++.exe" )
project(helloworld VERSION 1.0.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt6 REQUIRED COMPONENTS Core Widgets Gui)
qt_standard_project_setup()

add_subdirectory(custom_widgets)

add_executable(helloworld
    main.cpp
)

target_link_libraries(helloworld PRIVATE Qt6::Core Qt6::Widgets Qt6::Gui)

set_target_properties(helloworld PROPERTIES
    WIN32_EXECUTABLE ON
    MACOSX_BUNDLE ON
)