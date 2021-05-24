# SPDX-License-Identifier: Apache-2.0

cmake_minimum_required(VERSION 3.13.1)
# Re-direct the directory where the 'boards' directory is found from
# $ZEPHYR_BASE to this directory.
set(BOARD_ROOT ${CMAKE_CURRENT_LIST_DIR})

# This sample is only compatible with iote_ai_l552ze
set(BOARD iote_ai_l552ze)

find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(iote_ai_stm32l5)

target_sources(app PRIVATE src/main.c)
