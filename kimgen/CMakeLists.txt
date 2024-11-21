project(kimgen)
file(GLOB SRC *.h *.c)

find_package(PbOSCommon REQUIRED)
include_directories(${PbOSCommon_INCLUDE_DIR})

add_executable(kimgen ${SRC})
set_target_properties(
    kimgen
    PROPERTIES
    VS_DEBUGGER_COMMAND_ARGUMENTS "${PBOS_BINARY_DIR}/bootldr ${PBOS_BINARY_DIR}/pbkim ${PBOS_BINARY_DIR}/pbkim"
)

target_compile_definitions(kimgen PRIVATE -D_CRT_SECURE_NO_WARNINGS)
