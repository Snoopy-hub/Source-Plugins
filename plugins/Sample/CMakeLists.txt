add_library (
	Sample  
	SHARED
	engine_wrappers.h
	sample_mm.h
	sample_mm.cpp
)
configure_file(sample_mm.vdf sample_mm.vdf COPYONLY)
set_property(TARGET Sample PROPERTY CXX_STANDARD 14)
set_target_properties(Sample PROPERTIES PREFIX "")

include_directories(${directory_dependencies})

target_link_libraries(Sample ${library_dependencies})

list(APPEND ${definitions} SAMPLE_MM_EXPORTS)
add_compile_definitions(${definitions})
