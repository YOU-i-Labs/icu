add_executable(icuexportdata icuexportdata.cpp)

target_link_libraries(icuexportdata PUBLIC icutu icui18n icuuc)

install(
    TARGETS icuexportdata
    EXPORT "${TARGETS_EXPORT_NAME}"
    LIBRARY DESTINATION "${CMAKE_INSTALL_LIBDIR}"
    ARCHIVE DESTINATION "${CMAKE_INSTALL_LIBDIR}"
    RUNTIME DESTINATION "${CMAKE_INSTALL_BINDIR}"
    INCLUDES DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}"
)
