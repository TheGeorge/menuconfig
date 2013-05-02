cmake_minimum_required(VERSION 2.6)

include_directories("${PROJECT_SOURCE_DIR}/lxdialog")
add_subdirectory(lxdialog)

set(CURSES_USE_NCURSES TRUE)
find_package(Curses)

add_library(zconf zconf.tab.c)
add_library(conf conf.c)

add_executable(mconf mconf.c)

target_link_libraries(mconf lxdialog curses zconf conf)
