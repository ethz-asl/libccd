remake_project_header(config.h.remake INSTALL)
remake_include(${CMAKE_CURRENT_BINARY_DIR}/..)

remake_add_library(
  ccd PREFIX OFF
  LINK ${M_LIBRARY}
)
remake_add_headers()

remake_pkg_config_generate()
