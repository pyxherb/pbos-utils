project(cargen)
file(GLOB SRC *.h *.c)

find_package(PbOSCommon REQUIRED)
include_directories(${PbOSCommon_INCLUDE_DIR})

add_executable(cargen ${SRC})

target_compile_definitions(cargen PRIVATE -D_CRT_SECURE_NO_WARNINGS)
