add_executable(
    genrb
    errmsg.c
    filterrb.cpp
    genrb.cpp
    parse.cpp
    prscmnts.cpp
    rbutil.c
    read.c
    reslist.cpp
    rle.c
    ustr.c
    wrtjava.cpp
    wrtxml.cpp
)

target_link_libraries(genrb PUBLIC icutu icui18n icuuc)

install(
    TARGETS genrb
    EXPORT "${TARGETS_EXPORT_NAME}"
    LIBRARY DESTINATION "${CMAKE_INSTALL_LIBDIR}"
    ARCHIVE DESTINATION "${CMAKE_INSTALL_LIBDIR}"
    RUNTIME DESTINATION "${CMAKE_INSTALL_BINDIR}"
    INCLUDES DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}"
)

if(ICU_BUILD_IO)
  add_executable(derb derb.c)

  target_link_libraries(derb PUBLIC icuio icutu icui18n icuuc)

  install(
      TARGETS derb
      EXPORT "${TARGETS_EXPORT_NAME}"
      LIBRARY DESTINATION "${CMAKE_INSTALL_LIBDIR}"
      ARCHIVE DESTINATION "${CMAKE_INSTALL_LIBDIR}"
      RUNTIME DESTINATION "${CMAKE_INSTALL_BINDIR}"
      INCLUDES DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}"
  )
endif()
