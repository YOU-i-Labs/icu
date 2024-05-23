add_executable(escapesrc escapesrc.cpp)

target_link_libraries(escapesrc PUBLIC icutu icui18n icuuc)

install(
    TARGETS escapesrc
    EXPORT "${TARGETS_EXPORT_NAME}"
    LIBRARY DESTINATION "${CMAKE_INSTALL_LIBDIR}"
    ARCHIVE DESTINATION "${CMAKE_INSTALL_LIBDIR}"
    RUNTIME DESTINATION "${CMAKE_INSTALL_BINDIR}"
    INCLUDES DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}"
)
