# For more information about using CMake with Android Studio, read the
# documentation: https://d.android.com/studio/projects/add-native-code.html

# Sets the minimum version of CMake required to build the native library.

cmake_minimum_required(VERSION 3.4.1)

# Creates and names a library, sets it as either STATIC
# or SHARED, and provides the relative paths to its source code.
# You can define multiple libraries, and CMake builds them for you.
# Gradle automatically packages shared libraries with your APK.

add_subdirectory(ogre)

# Include necessary submodules
set(CMAKE_MODULE_PATH
"${CMAKE_SOURCE_DIR}/ogre/CMake"
"${CMAKE_SOURCE_DIR}/ogre/CMake/Utils"
"${CMAKE_SOURCE_DIR}/ogre/CMake/Packages"
)

include(CMakeDependentOption)
include(MacroLogFeature)
include(OgreConfigTargets)
include(PreprocessorUtils)
set(OGRE_TEMPLATES_DIR "${OGRE_SOURCE_DIR}/CMake/Templates")

add_subdirectory(src/main/cpp demo)
