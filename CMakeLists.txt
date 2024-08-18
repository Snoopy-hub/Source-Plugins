cmake_minimum_required(VERSION 3.8)
project("Source.Plugins")

set(
    directory_dependencies
	${CMAKE_CURRENT_SOURCE_DIR}/metamod-source/core
	${CMAKE_CURRENT_SOURCE_DIR}/metamod-source/core/sourcehook
	${CMAKE_CURRENT_SOURCE_DIR}/hl2sdk-l4d2/public
	${CMAKE_CURRENT_SOURCE_DIR}/hl2sdk-l4d2/public/engine
	${CMAKE_CURRENT_SOURCE_DIR}/hl2sdk-l4d2/public/game/server
	${CMAKE_CURRENT_SOURCE_DIR}/hl2sdk-l4d2/public/tier0
	${CMAKE_CURRENT_SOURCE_DIR}/hl2sdk-l4d2/public/tier1
	${CMAKE_CURRENT_SOURCE_DIR}/hl2sdk-l4d2/public/vstdlib
)
link_directories(
	${CMAKE_CURRENT_SOURCE_DIR}/hl2sdk-l4d2/lib/linux
)
set(
	library_dependencies
	libtier0_srv.so
	libvstdlib_srv.so
	-l:tier1_i486.a
)

set(
    definitions
	SOURCE_ENGINE=9
	_LINUX
	stricmp=strcasecmp
	_vsnprintf=vsnprintf
	SE_EPISODE1=1
	SE_DARKMESSIAH=2
	SE_ORANGEBOX=3
	SE_BLOODYGOODTIME=4
	SE_EYE=5
	SE_CSS=6
	SE_ORANGEBOXVALVE=7
	SE_LEFT4DEAD=8
	SE_LEFT4DEAD2=9
	SE_ALIENSWARM=10
	SE_PORTAL2=1
	SE_CSGO=12
)

add_subdirectory("plugins")
