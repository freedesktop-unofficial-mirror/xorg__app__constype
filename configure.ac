dnl $Id$
dnl
dnl Copyright 2005 Sun Microsystems, Inc.  All rights reserved.
dnl 
dnl Permission is hereby granted, free of charge, to any person obtaining a
dnl copy of this software and associated documentation files (the
dnl "Software"), to deal in the Software without restriction, including
dnl without limitation the rights to use, copy, modify, merge, publish,
dnl distribute, and/or sell copies of the Software, and to permit persons
dnl to whom the Software is furnished to do so, provided that the above
dnl copyright notice(s) and this permission notice appear in all copies of
dnl the Software and that both the above copyright notice(s) and this
dnl permission notice appear in supporting documentation.
dnl 
dnl THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
dnl OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
dnl MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT
dnl OF THIRD PARTY RIGHTS. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR
dnl HOLDERS INCLUDED IN THIS NOTICE BE LIABLE FOR ANY CLAIM, OR ANY SPECIAL
dnl INDIRECT OR CONSEQUENTIAL DAMAGES, OR ANY DAMAGES WHATSOEVER RESULTING
dnl FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT,
dnl NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION
dnl WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
dnl 
dnl Except as contained in this notice, the name of a copyright holder
dnl shall not be used in advertising or otherwise to promote the sale, use
dnl or other dealings in this Software without prior written authorization
dnl of the copyright holder.
dnl 
dnl
dnl Process this file with autoconf to create configure.

AC_PREREQ([2.57])
AC_INIT(constype,[0.99.0],
	[https://bugs.freedesktop.org/enter_bug.cgi?product=xorg],constype)
AM_INIT_AUTOMAKE([dist-bzip2])
AM_MAINTAINER_MODE

AM_CONFIG_HEADER(config.h)

AC_PROG_CC
AC_PROG_INSTALL
XORG_PROG_RAWCPP

AC_HEADER_STDC
AC_CHECK_HEADERS([sys/visual_io.h sys/fbio.h machine/fbio.h sun/fbio.h],
	[BUILD_CONSTYPE=yes])

AM_CONDITIONAL(BUILD_CONSTYPE, [test x$BUILD_CONSTYPE = xyes])

XORG_RELEASE_VERSION

AC_OUTPUT([Makefile])
