set(includes)
set(srcs)
set(priv_includes)

include(${CMAKE_CURRENT_LIST_DIR}/espcliFilePaths.cmake)

list(APPEND includes ${ESP_CLI_INCLUDE_PUBLIC_DIRS})

list(APPEND srcs ${ESP_CLI_SOURCES})
				  
idf_component_register(SRCS "${srcs}"
                       INCLUDE_DIRS "${includes}"
                       PRIV_INCLUDE_DIRS ""
                       REQUIRES "")

target_linker_script(${COMPONENT_LIB} INTERFACE "cli.ld")
