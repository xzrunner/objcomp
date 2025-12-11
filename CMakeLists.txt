cmake_minimum_required(VERSION 3.16)

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

add_library(${PROJECT_NAME} STATIC ${ALL_FILES})

target_include_directories(${PROJECT_NAME} PRIVATE include external/guard/include)
