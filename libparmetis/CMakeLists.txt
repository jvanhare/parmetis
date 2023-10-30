# Include directories for library code.
include_directories(.)
include_directories(${CMAKE_BINARY_DIR}/metis/include)
# Find sources.
file(GLOB parmetis_sources *.c)
# Create libparmetis
add_library(parmetis ${ParMETIS_LIBRARY_TYPE} ${parmetis_sources})
target_include_directories(parmetis PUBLIC ${MPI_C_INCLUDE_DIRS})

# Link with metis and MPI libraries.
target_link_libraries(parmetis metis ${MPI_C_LIBRARIES})

install(TARGETS parmetis
  LIBRARY DESTINATION lib
  RUNTIME DESTINATION lib
  ARCHIVE DESTINATION lib)
