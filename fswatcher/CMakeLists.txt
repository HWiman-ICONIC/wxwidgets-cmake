# Define a variable containing a list of source files for the project
set(SRC_FILES
    fswatcher.cpp
    )

if(WIN32)
    # Include a RC file for windows
    list(APPEND SRC_FILES ../sample.rc)
elseif(APPLE)
    # Add an icon for the apple .app file
    list(APPEND SRC_FILES ../../src/osx/carbon/wxmac.icns)
endif()

# Define the build target for the executable
add_executable(fswatcher WIN32 MACOSX_BUNDLE ${SRC_FILES})

target_include_directories(fswatcher
    PUBLIC
        $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include>
)

# Link required libraries to the executable
target_link_libraries(fswatcher ${wxWidgets_LIBRARIES})

if(APPLE)
    set_target_properties(fswatcher PROPERTIES
        RESOURCE "../../src/osx/carbon/wxmac.icns"
        MACOSX_BUNDLE_ICON_FILE wxmac.icns
        MACOSX_BUNDLE_COPYRIGHT "Copyright wxWidgets"
        MACOSX_BUNDLE_GUI_IDENTIFIER "org.wxwidgets.webview"
        )
endif()
