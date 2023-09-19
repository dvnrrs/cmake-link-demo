This repository demonstrates how to link a CMake target against a shared
library in a fixed location (i.e. not necessarily installed in the usual
way in `/usr/lib`).

First, build the `libsample.so` shared library:

    cd sample
    make

This produces a `libsample.so` file in the `sample/` directory. Then,
build the demo with CMake:

    mkdir build
    cd build
    cmake ..
    make

Linking is done in `CMakeLists.txt` as follows:

    # relative path is interpreted relative to the location of
    # this CMakeLists.txt file (${CMAKE_CURRENT_SOURCE_DIR})
    target_link_directories(${PROJECT_NAME} PRIVATE libsample)

    # links in `libsample.so`
    target_link_libraries(${PROJECT_NAME} PRIVATE sample)
