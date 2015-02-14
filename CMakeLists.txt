cmake_minimum_required (VERSION 2.6)
project (Tutorial)
#find_package(wxWidgets COMPONENTS core base REQUIRED)
#include( "${wxWidgets_USE_FILE}" )


#PROJECT(Test)
SET(wxWidgets_USE_LIBS)
FIND_PACKAGE(wxWidgets)
IF(wxWidgets_FOUND)
    INCLUDE("${wxWidgets_USE_FILE}")
    add_executable(tut main.cpp)
    # and for each of your dependant executable/library targets:
    TARGET_LINK_LIBRARIES(tut ${wxWidgets_LIBRARIES})
ELSE(wxWidgets_FOUND)
    # For convenience. When we cannot continue, inform the user
    MESSAGE("wxWidgets not found!")
ENDIF(wxWidgets_FOUND)


