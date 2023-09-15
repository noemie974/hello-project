set(target_name Basic)
add_library(${target_name} STATIC "")
target_sources(${target_name}
 PRIVATE "${PROJECT_SOURCE_DIR}/Src/Basic/message.cpp"
 PRIVATE "${PROJECT_SOURCE_DIR}/Include/Basic/message.h"
)
target_include_directories(${target_name} 
 PUBLIC 
 $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/Include>
 $<BUILD_INTERFACE:${PROJECT_BINARY_DIR}>
 $<INSTALL_INTERFACE:Include>

)
export(TARGETS ${target_name} FILE 
${PROJECT_BINARY_DIR}/${target_name}_target.cmake )

#install target lib
install(TARGETS ${target_name} 
EXPORT ${target_name} 
DESTINATION lib
)
#install target export
install(EXPORT ${target_name} 
FILE ${target_name}_target.cmake 
DESTINATION cmake/
)
#install includes
install(DIRECTORY ${PROJECT_SOURCE_DIR}/Include/ 
DESTINATION Include/
)
#generated include
install(FILES ${PROJECT_BINARY_DIR}/HelloProjConfig.h 
DESTINATION include/)
