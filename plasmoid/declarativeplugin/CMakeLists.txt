include_directories(${CMAKE_CURRENT_BINARY_DIR}
                    ${CMAKE_CURRENT_SOURCE_DIR}
                    ${CMAKE_SOURCE_DIR}
                    ${CMAKE_BINARY_DIR})
set(kdeconnectdeclarativeplugin_SRC
    batteryinterface.cpp
    kdeconnectdeclarativeplugin.cpp
)

kde4_add_library(kdeconnectdeclarativeplugin SHARED ${kdeconnectdeclarativeplugin_SRC})
add_dependencies(kdeconnectdeclarativeplugin libkdeconnect)
target_link_libraries(kdeconnectdeclarativeplugin
    ${KDE4_KDEUI_LIBS}
    ${KDE4_KDECORE_LIBS}
    ${QT_QTCORE_LIBRARY}
    ${QT_QTGUI_LIBRARY}
    ${QT_QTDECLARATIVE_LIBRARY}
    kdeconnect
)
install(TARGETS kdeconnectdeclarativeplugin DESTINATION ${IMPORTS_INSTALL_DIR}/org/kde/kdeconnect)
install(FILES qmldir DESTINATION ${IMPORTS_INSTALL_DIR}/org/kde/kdeconnect)
