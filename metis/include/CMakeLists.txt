configure_file(${CMAKE_CURRENT_SOURCE_DIR}/metis.h.in
               ${CMAKE_CURRENT_BINARY_DIR}/metis.h @ONLY)

if(METIS_INSTALL)
  install(FILES ${CMAKE_CURRENT_BINARY_DIR}/metis.h DESTINATION include)
endif()
