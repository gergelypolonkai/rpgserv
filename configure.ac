AC_INIT([RPGServ], [0.1.0])

AC_CONFIG_HEADERS([config.h])
AC_CONFIG_SRCDIR([configure.ac])

PACKAGE=rpgserv
VERSION=0.1.0

AM_INIT_AUTOMAKE($PACKAGE, $VERSION)

AC_ARG_ENABLE([memcached], AS_HELP_STRING([--enable-memcached],[Build with memcached support (default: yes)]), [], [enable_memcached=yes])
AM_CONDITIONAL([ENABLE_MEMCACHED], [test "$enable_memcached" = "yes"])

if test "$enable_memcached" = "yes"; then
	PKG_CHECK_MODULES(MEMCACHED, libmemcached)
	AC_DEFINE([ENABLE_MEMCACHED], [1], [Define to compile with memcached support])
fi

AC_PROG_CC
AC_OUTPUT(Makefile src/Makefile)

