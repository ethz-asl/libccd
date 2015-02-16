remake_find_library(m math.h)

remake_project_option(DOUBLE_PRECISION "double precision support" OFF)
remake_project_get(DOUBLE_PRECISION OUTPUT CCD_DOUBLE)

if (CCD_DOUBLE)
  remake_set(CCD_DOUBLE ON)
else()
  remake_set(CCD_SINGLE ON)
endif()

remake_include(lib)
remake_add_directories(lib bin)
