project(kbblgen)
file(GLOB SRC *.h *.c)

find_package(PbOSCommon REQUIRED)
include_directories(${PbOSCommon_INCLUDE_DIR})

add_executable(kbblgen ${SRC})

target_compile_definitions(kbblgen PRIVATE -D_CRT_SECURE_NO_WARNINGS)
