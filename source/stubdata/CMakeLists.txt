add_library(icustubdata stubdata.c)

if(U_USING_ICU_NAMESPACE)
  target_compile_definitions(icustubdata PUBLIC U_USING_ICU_NAMESPACE=1)
else()
  target_compile_definitions(icustubdata PUBLIC U_USING_ICU_NAMESPACE=0)
endif()

if(NOT BUILD_SHARED_LIBS)
  target_compile_definitions(icustubdata PUBLIC U_STATIC_IMPLEMENTATION)
endif()

target_include_directories(
    icustubdata
    PRIVATE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/../common>
)

if(ICU_DATA_ARCHIVE_MODE)
  install(
      TARGETS icustubdata
      EXPORT "${TARGETS_EXPORT_NAME}"
      LIBRARY DESTINATION "${CMAKE_INSTALL_LIBDIR}"
      ARCHIVE DESTINATION "${CMAKE_INSTALL_LIBDIR}"
      RUNTIME DESTINATION "${CMAKE_INSTALL_BINDIR}"
      INCLUDES DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}"
  )
endif()

set_target_properties(
    icustubdata
    PROPERTIES
    EXPORT_NAME data
    OUTPUT_NAME icudata
)
