
rock_find_qt5(OPTIONAL)
rock_find_qt4(OPTIONAL)

if (ROCK_QT_VERSION_4)
    rock_vizkit_plugin(rock_tutorial-viz
        RockVisualization.cpp
        MOC RockVisualization.hpp
        DEPS_PKGCONFIG base-types
        HEADERS RockVisualization.hpp)
endif()

if (ROCK_QT_VERSION_5)
    rock_vizkit_plugin_qt5(rock_tutorial-viz-qt5
        RockVisualization.cpp
        MOC5 RockVisualization.hpp
        DEPS_PKGCONFIG base-types
        HEADERS RockVisualization.hpp)
endif()

install(FILES
    ${PROJECT_SOURCE_DIR}/resources/rock.osg
    ${PROJECT_SOURCE_DIR}/resources/rock.png
    DESTINATION share/vizkit3d
    )
