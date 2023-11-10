cmake_minimum_required(VERSION 3.24)

project(uglobalhotkeys)

find_package(Qt6 COMPONENTS Core Widgets Gui REQUIRED)

if(UNIX)
find_package(X11 COMPONENTS xcb keysyms)
endif()

set(SRCS     
  ${CMAKE_CURRENT_SOURCE_DIR}/ukeysequence.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/uglobalhotkeys.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/uexception.cpp
)

add_library(${PROJECT_NAME} STATIC ${SRCS})
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(${PROJECT_NAME} Qt6::Widgets Qt6::Core Qt6::Gui Qt6::GuiPrivate)
if(UNIX)
target_link_libraries(${PROJECT_NAME} xcb keysyms)
endif()