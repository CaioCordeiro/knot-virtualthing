AC_PREREQ(2.60)
AC_INIT([knot-virtual-thing], [0.01], [alla@cesar.org.br])

AC_CONFIG_AUX_DIR([m4])
AM_INIT_AUTOMAKE([silent-rules foreign subdir-objects])

AC_CONFIG_HEADERS(config.h)

m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

AM_MAINTAINER_MODE

AC_PREFIX_DEFAULT(/usr/local)

PKG_PROG_PKG_CONFIG

COMPILER_WARNING_CFLAGS
COMPILER_BUILD_CFLAGS

AC_LANG_C

AC_PROG_CC
AC_PROG_CC_PIE

m4_define([_LT_AC_TAGCONFIG], [])
m4_ifdef([AC_LIBTOOL_TAGS], [AC_LIBTOOL_TAGS([])])

AC_DISABLE_STATIC
AC_PROG_LIBTOOL

AC_ARG_WITH([check], AS_HELP_STRING([--with-check], [Enables testing]))
AS_IF([test "x$with_check" = "xyes"],
  [PKG_CHECK_MODULES([CHECK], [check >= 0.10.0])])

PKG_CHECK_MODULES(ELL, ell,
  [AC_DEFINE([HAVE_ELL],[1],[Use ELL])],
  [AC_MSG_ERROR("ell missing")])
AC_SUBST(ELL_CFLAGS)
AC_SUBST(ELL_LIBS)

PKG_CHECK_MODULES(KNOTCLOUDSDK, knotcloudsdkc,
  [AC_DEFINE([HAVE_KNOTCLOUDSDK],[1],[Use KNOTCLOUDSDK])],
  [AC_MSG_ERROR("knotcloudsdkc missing")])
AC_SUBST(KNOTCLOUDSDK_CFLAGS)
AC_SUBST(KNOTCLOUDSDK_LIBS)

PKG_CHECK_MODULES(KNOTPROTO, knotprotocol,
  [AC_DEFINE([HAVE_KNOTPROTO],[1],[Use KNOTPROTO])],
  [AC_MSG_ERROR("knotprotocol missing")])
AC_SUBST(KNOTPROTO_CFLAGS)
AC_SUBST(KNOTPROTO_LIBS)

PKG_CHECK_MODULES(MODBUS, libmodbus,
  [AC_DEFINE([HAVE_MODBUS],[1],[Use MODBUS])],
  [AC_MSG_ERROR("modbus missing")])
AC_SUBST(MODBUS_CFLAGS)
AC_SUBST(MODBUS_LIBS)

AC_OUTPUT(Makefile)
