cmake_minimum_required(VERSION 3.8)

project(objcomp)

################################################################################
# Source groups
################################################################################
set(no_group_source_files
    "include/objcomp/Object.inl"
)
source_group("" FILES ${no_group_source_files})

set(Headers
    "include/objcomp/Component.h"
    "include/objcomp/Object.h"
)
source_group("Headers" FILES ${Headers})

set(Sources
    "source/Component.cpp"
    "source/Object.cpp"
)
source_group("Sources" FILES ${Sources})

set(ALL_FILES
    ${no_group_source_files}
    ${Headers}
    ${Sources}
)

include_directories(${CMAKE_SOURCE_DIR}/include)
include_directories(../guard/include)

add_library(objcomp STATIC ${ALL_FILES})

#target_compile_features(brepdb PRIVATE cxx_std_17)
