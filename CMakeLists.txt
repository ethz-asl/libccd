cmake_minimum_required(VERSION 2.6)

include(ReMake)

remake_project(
  libccd
  VERSION 1.5
  RELEASE beta
  SUMMARY "Library for collision detection between two convex shapes."
  AUTHOR "Daniel Fiser"
  CONTACT "ralf.kaestner@gmail.com"
  HOME "http://libccd.danfis.cz"
  LICENSE "BSD License (BSD)"
  README README.md
  PREFIX ccd-
  INSTALL /usr
  HEADER_DESTINATION include/ccd
)

remake_doc(
  html
)

remake_pack_deb(
)
remake_pack_deb(
  COMPONENT dev
  DESCRIPTION "development headers"
  DEPENDS libccd
)
remake_pack_deb(
  ARCH all
  COMPONENT doc
  DESCRIPTION "documentation"
)

remake_distribute_deb(
  DISTRIBUTION lucid
  SECTION libs
  UPLOAD ppa:kralf/asl
  DEPENDS python-sphinx remake doxygen pkg-config
  PASS CMAKE_BUILD_TYPE LIBCCD_GIT_REVISION
)
remake_distribute_deb(
  DISTRIBUTION precise
  SECTION libs
  UPLOAD ppa:kralf/asl
  DEPENDS python-sphinx remake doxygen pkg-config
  PASS CMAKE_BUILD_TYPE LIBCCD_GIT_REVISION
)
remake_distribute_deb(
  DISTRIBUTION trusty
  SECTION libs
  UPLOAD ppa:kralf/asl
  DEPENDS python-sphinx remake doxygen pkg-config
  PASS CMAKE_BUILD_TYPE LIBCCD_GIT_REVISION
)
