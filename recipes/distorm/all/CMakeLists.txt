cmake_minimum_required(VERSION 3.1)
project(cmake_wrapper)

include(conanbuildinfo.cmake)
conan_basic_setup()

set(DISTORM_PATH source_subfolder/)
set(DISTORM_SRC_DIR ${DISTORM_PATH}/src/)
set(DISTORM_SOURCES ${DISTORM_SRC_DIR}/decoder.c ${DISTORM_SRC_DIR}/distorm.c ${DISTORM_SRC_DIR}/instructions.c
  ${DISTORM_SRC_DIR}/insts.c ${DISTORM_SRC_DIR}/mnemonics.c ${DISTORM_SRC_DIR}/operands.c
  ${DISTORM_SRC_DIR}/prefix.c ${DISTORM_SRC_DIR}/textdefs.c)
add_library(distorm STATIC ${DISTORM_SOURCES})

INSTALL(TARGETS distorm DESTINATION lib)
