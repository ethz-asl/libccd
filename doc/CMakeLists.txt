remake_add_documentation(
  CUSTOM Sphinx
  sphinx-build -q -b %TYPE% ${CMAKE_CURRENT_SOURCE_DIR} %OUTPUT%
  INPUT conf.py *.rst
  TYPE html
)
