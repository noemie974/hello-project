set(target_name Basic)
add_library(${target_name} STATIC "")
target_sources(${target_name}
 PRIVATE "${PROJECT_SOURCE_DIR}/Src/Basic/message.cpp"
 PRIVATE "${PROJECT_SOURCE_DIR}/Include/Basic/message.h"
)
target_include_directories(${target_name} 
 PUBLIC 
 "${PROJECT_SOURCE_DIR}/Include"
 "${PROJECT_BINARY_DIR}"
)