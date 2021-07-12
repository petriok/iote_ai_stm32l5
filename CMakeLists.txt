# SPDX-License-Identifier: Apache-2.0

cmake_minimum_required(VERSION 3.13.1)
# Re-direct the directory where the 'boards' directory is found from
# $ZEPHYR_BASE to this directory.
set(BOARD_ROOT ${CMAKE_CURRENT_LIST_DIR})

# This sample is only compatible with iote_ai_l552ze
set(BOARD iote_ai_l552ze)

find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(iote_ai_stm32l5)

# A simple Blinky test
#target_sources(app PRIVATE src/main.c)

# A simple IMU test
#target_sources(app PRIVATE src/main_mpu6050.c)

# A simple shell test
target_sources(app PRIVATE src/main_shell.c src/test_module.c)
target_sources_ifdef(CONFIG_SHELL_DYNAMIC_CMDS app PRIVATE src/dynamic_cmd.c src/qsort.c)
target_sources_ifdef(CONFIG_SHELL_BACKEND_SERIAL app PRIVATE src/uart_reinit.c)

# For overriding the clock control
#target_sources(app PRIVATE src/stm32_hal/clock_config.c)
