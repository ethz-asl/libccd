remake_include()
remake_test_target(
  cu
  main.c common.c common.h support.c support.h vec3.c vec3.h polytope.c
    polytope.h boxbox.c boxbox.h spheresphere.c spheresphere.h cylcyl.c
    cylcyl.h boxcyl.c boxcyl.h mpr_boxbox.c mpr_boxbox.h mpr_cylcyl.c
    mpr_cylcyl.h mpr_boxcyl.c mpr_boxcyl.h cu/cu.c cu/cu.h
  LINK ccd ${}
  COMMAND_ARGS ${CMAKE_CURRENT_BINARY_DIR}/
)

remake_define(CU_ENABLE_TIMER ON)
remake_add_executable(
  bench
  bench.c support.c support.h cu/cu.c cu/cu.h
  LINK ccd ${RT_LIBRARY}
)
remake_add_executable(
  bench2
  bench2.c support.c support.h cu/cu.c cu/cu.h
  LINK ccd ${RT_LIBRARY}
)
