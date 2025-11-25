cmake_minimum_required(VERSION 3.4.1)  # for example
add_library( convertImage
    # Sets the library as a shared library.
    SHARED
    # Provides a relative path to your source file(s).
    ../ios/native/converter.c
)

# Support for 16KB page size (required for Android 15+)
# Set max page size to 16KB (16384 bytes) or 64KB (65536 bytes)
target_link_options(convertImage PRIVATE
    -Wl,-z,max-page-size=16384
)