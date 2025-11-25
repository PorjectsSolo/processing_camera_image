cmake_minimum_required(VERSION 3.4.1)  # for example

# Support for 16KB page size (required for Android 15+)
# Set linker flags before creating the library
set(CMAKE_SHARED_LINKER_FLAGS "${CMAKE_SHARED_LINKER_FLAGS} -Wl,-z,max-page-size=16384")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -Wl,-z,max-page-size=16384")

add_library( convertImage
    # Sets the library as a shared library.
    SHARED
    # Provides a relative path to your source file(s).
    ../ios/native/converter.c
)