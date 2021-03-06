# CMakeLists.txt for the ZoneMinder perl scripts.

# Process the perl modules subdirectory
add_subdirectory(ZoneMinder)

# Create files from the .in files
configure_file(zmaudit.pl.in "${CMAKE_CURRENT_BINARY_DIR}/zmaudit.pl" @ONLY)
configure_file(zmcontrol.pl.in "${CMAKE_CURRENT_BINARY_DIR}/zmcontrol.pl" @ONLY)
configure_file(zmdc.pl.in "${CMAKE_CURRENT_BINARY_DIR}/zmdc.pl" @ONLY)
configure_file(zmfilter.pl.in "${CMAKE_CURRENT_BINARY_DIR}/zmfilter.pl" @ONLY)
configure_file(zmpkg.pl.in "${CMAKE_CURRENT_BINARY_DIR}/zmpkg.pl" @ONLY)
configure_file(zmtrack.pl.in "${CMAKE_CURRENT_BINARY_DIR}/zmtrack.pl" @ONLY)
configure_file(zmtrigger.pl.in "${CMAKE_CURRENT_BINARY_DIR}/zmtrigger.pl" @ONLY)
configure_file(zmupdate.pl.in "${CMAKE_CURRENT_BINARY_DIR}/zmupdate.pl" @ONLY)
configure_file(zmvideo.pl.in "${CMAKE_CURRENT_BINARY_DIR}/zmvideo.pl" @ONLY)
configure_file(zmwatch.pl.in "${CMAKE_CURRENT_BINARY_DIR}/zmwatch.pl" @ONLY)
configure_file(zmcamtool.pl.in "${CMAKE_CURRENT_BINARY_DIR}/zmcamtool.pl" @ONLY)
if(NOT ZM_NO_X10)
	configure_file(zmx10.pl.in "${CMAKE_CURRENT_BINARY_DIR}/zmx10.pl" @ONLY)
endif(NOT ZM_NO_X10)
#configure_file(zmdbbackup.in zmdbbackup @ONLY)
#configure_file(zmdbrestore.in zmdbrestore @ONLY)
configure_file(zm.in "${CMAKE_CURRENT_BINARY_DIR}/zm" @ONLY)
#configure_file(zmeventdump.in zmeventdump @ONLY)

# Install the perl scripts
install(FILES "${CMAKE_CURRENT_BINARY_DIR}/zmaudit.pl" "${CMAKE_CURRENT_BINARY_DIR}/zmcontrol.pl" "${CMAKE_CURRENT_BINARY_DIR}/zmdc.pl" "${CMAKE_CURRENT_BINARY_DIR}/zmfilter.pl" "${CMAKE_CURRENT_BINARY_DIR}/zmpkg.pl" "${CMAKE_CURRENT_BINARY_DIR}/zmtrack.pl" "${CMAKE_CURRENT_BINARY_DIR}/zmtrigger.pl" "${CMAKE_CURRENT_BINARY_DIR}/zmupdate.pl" "${CMAKE_CURRENT_BINARY_DIR}/zmvideo.pl" "${CMAKE_CURRENT_BINARY_DIR}/zmwatch.pl" "${CMAKE_CURRENT_BINARY_DIR}/zmcamtool.pl" DESTINATION "${CMAKE_INSTALL_FULL_BINDIR}" PERMISSIONS OWNER_WRITE OWNER_READ OWNER_EXECUTE GROUP_READ GROUP_EXECUTE WORLD_READ WORLD_EXECUTE)
if(NOT ZM_NO_X10)
	install(FILES "${CMAKE_CURRENT_BINARY_DIR}/zmx10.pl" DESTINATION "${CMAKE_INSTALL_FULL_BINDIR}" PERMISSIONS OWNER_WRITE OWNER_READ OWNER_EXECUTE GROUP_READ GROUP_EXECUTE WORLD_READ WORLD_EXECUTE)
endif(NOT ZM_NO_X10)
