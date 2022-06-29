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
	fips_vs_disable_warnings(4312)
	fips_dir(md5)
	fips_files( 
		md5.c   
		md5.h   		     
    	)
fips_end_lib() 


if (NOT FIPS_IMPORT)
    fips_finish()
endif()