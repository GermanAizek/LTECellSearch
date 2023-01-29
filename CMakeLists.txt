cmake_minimum_required(VERSION 3.5)

project(LTECellSearch LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

#include_directories(${PROJECT_SOURCE_DIR})
include_directories(${PROJECT_SOURCE_DIR}/srsRAN/lib/include)
include_directories(${PROJECT_SOURCE_DIR}/srsRAN)

add_subdirectory(srsRAN)

add_executable(${PROJECT_NAME} main.cpp srsran_include.h)

target_link_libraries(${PROJECT_NAME} srsue_phy srsenb_phy srsran_phy srsran_common srsran_rf)
