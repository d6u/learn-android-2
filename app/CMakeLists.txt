# Sets the minimum version of CMake required to build your native library.
# This ensures that a certain set of CMake features is available to
# your build.

cmake_minimum_required(VERSION 3.4.1)

# Specifies a library name, specifies whether the library is STATIC or
# SHARED, and provides relative paths to the source code. You can
# define multiple libraries by adding multiple add_library() commands,
# and CMake builds them for you. When you build your app, Gradle
# automatically packages shared libraries with your APK.

add_library( # Specifies the name of the library.
             awesome-native

             # Sets the library as a shared library.
             SHARED

             # Provides a relative path to your source file(s).
             src/main/cpp/awesome-native.cpp )

find_library(log-lib log)
find_library(android-lib android)

#find_library( # Defines the name of the path variable that stores the
#              # location of the NDK library.
#              base-lib
#
#              # Specifies the name of the NDK library that
#              # CMake needs to locate.
#              libbase )

# Links your native library against one or more other native libraries.
target_link_libraries( # Specifies the target library.
                       awesome-native

                       # Links the log library to the target library.
                       ${log-lib}
                       ${android-lib})
