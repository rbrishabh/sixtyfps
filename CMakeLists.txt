# LICENSE BEGIN
# This file is part of the SixtyFPS Project -- https://sixtyfps.io
# Copyright (c) 2020 Olivier Goffart <olivier.goffart@sixtyfps.io>
# Copyright (c) 2020 Simon Hausmann <simon.hausmann@sixtyfps.io>
#
# SPDX-License-Identifier: GPL-3.0-only
# This file is also available under commercial licensing terms.
# Please contact info@sixtyfps.io for more information.
# LICENSE END
cmake_minimum_required(VERSION 3.16)

project(SixtyFPS LANGUAGES CXX)
include(CTest)

add_subdirectory(api/sixtyfps-cpp/)
add_subdirectory(examples/printerdemo/cpp/)
add_subdirectory(examples/printerdemo/cpp_interpreted/)
add_subdirectory(examples/printerdemo_old/cpp/)
add_subdirectory(examples/todo/cpp/)
add_subdirectory(examples/gallery/)
add_subdirectory(examples/memory/)
add_subdirectory(examples/qt_viewer/)
# iot-dashboard uses fmtlib via FetchContent and 3.16 has a bug
# configuring it (issue #232)
if (CMAKE_VERSION VERSION_GREATER_EQUAL 3.17.0)
    add_subdirectory(examples/iot-dashboard/)
endif()
