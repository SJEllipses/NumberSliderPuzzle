cmake_minimum_required(VERSION 3.10)
project(NumberSliderPuzzle)

set(CMAKE_CXX_STANDARD 11)

find_package(OpenCV REQUIRED)

add_executable(NumberSliderPuzzle
    main.cpp
    ImageProcess.cpp
    MathProcess.cpp
    InputProcess.cpp)

target_link_libraries(NumberSliderPuzzle PRIVATE ${OpenCV_LIBS})

if(MINGW)
    if(CMAKE_BUILD_TYPE STREQUAL "Debug")
        set_target_properties(NumberSliderPuzzle PROPERTIES LINK_FLAGS "-mconsole")
    else()
        set_target_properties(NumberSliderPuzzle PROPERTIES LINK_FLAGS "-mwindows")
    endif()
endif()