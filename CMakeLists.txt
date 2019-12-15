cmake_minimum_required(VERSION 3.10)

set ( CMAKE_C_FLAGS "-fPIC")
set(INSTALL_PREFIX "/usr/local/lib")

project(te923)

add_library(te923 te923con.c te923usb.c te923com.c )

add_executable(te923exe te923con.c te923com.c te923usb.c)

install(TARGETS te923 LIBRARY DESTINATION ${INSTALL_PREFIX})

target_link_libraries(te923 -lusb)
target_link_libraries(te923exe -lusb)
