#
# project: fips-md5
#
if (NOT FIPS_IMPORT)
    cmake_minimum_required(VERSION 3.0)
	get_filename_component(FIPS_ROOT_DIR "../fips" ABSOLUTE)
	include("${FIPS_ROOT_DIR}/cmake/fips.cmake")
	fips_setup()
    fips_project(fips-RenderCore)
endif()

fips_begin_lib(md5)
	fips_dir(md5)
	fips_files( 
		md5.c   
		md5.h   		     
    	)
fips_end_lib(md5) 
if (FIPS_CLANG)
    set_target_properties(md5 PROPERTIES COMPILE_FLAGS "-Wno-shift-negative-value")
endif()
