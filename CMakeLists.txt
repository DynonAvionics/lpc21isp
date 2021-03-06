cmake_minimum_required (VERSION 3.1 FATAL_ERROR)

option (GPIO_SUPPORT "enable gpio support" OFF)

project (lpc21isp
         DESCRIPTION "lpc21isp flasher app"
         LANGUAGES C)

set (def)

if (GPIO_SUPPORT)
  set (def GPIO_SUPPORT)
  message("Building with GPIO_SUPPORT")
else ()
  message("Building without GPIO_SUPPORT")
endif ()

set (inc
  adprog.h
  lpc21isp.h
  lpcprog.h
  lpcterm.h)

set (src
  adprog.c
  lpc21isp.c
  lpcprog.c
  lpcterm.c)

add_executable (${PROJECT_NAME} ${src})
target_compile_definitions (${PROJECT_NAME} PRIVATE ${def})
target_compile_features (${PROJECT_NAME} PRIVATE c_std_11)
target_compile_options (${PROJECT_NAME} PRIVATE -Wall -Wextra)
target_include_directories (${PROJECT_NAME} PRIVATE ${inc})
