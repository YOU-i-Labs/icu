add_executable(
    makeconv
    makeconv.c
    ucnvstat.c
    genmbcs.cpp
    gencnvex.c
)

target_link_libraries(makeconv PUBLIC icutu icui18n icuuc)

install(
    TARGETS makeconv
    EXPORT "${TARGETS_EXPORT_NAME}"
    LIBRARY DESTINATION "${CMAKE_INSTALL_LIBDIR}"
    ARCHIVE DESTINATION "${CMAKE_INSTALL_LIBDIR}"
    RUNTIME DESTINATION "${CMAKE_INSTALL_BINDIR}"
    INCLUDES DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}"
)
