#
# Copyright (c) 2005, Oracle and/or its affiliates. All rights reserved.
#
# Permission is hereby granted, free of charge, to any person obtaining a
# copy of this software and associated documentation files (the "Software"),
# to deal in the Software without restriction, including without limitation
# the rights to use, copy, modify, merge, publish, distribute, sublicense,
# and/or sell copies of the Software, and to permit persons to whom the
# Software is furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice (including the next
# paragraph) shall be included in all copies or substantial portions of the
# Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL
# THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
# FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
# DEALINGS IN THE SOFTWARE.
#

if BUILD_CONSTYPE

bin_PROGRAMS = constype

constype_SOURCES = constype.c

AM_CFLAGS = $(CWARNFLAGS)

appman_PRE = constype.man

appmandir = $(APP_MAN_DIR)

appman_DATA = $(appman_PRE:man=@APP_MAN_SUFFIX@)

CLEANFILES = $(appman_DATA)

SED = sed

# Strings to replace in man pages
XORGRELSTRING = @PACKAGE_STRING@
  XORGMANNAME = X Version 11

MAN_SUBSTS = \
        -e 's|__vendorversion__|"$(XORGRELSTRING)" "$(XORGMANNAME)"|' \
        -e 's|__xorgversion__|"$(XORGRELSTRING)" "$(XORGMANNAME)"|' \
        -e 's|__xservername__|Xorg|g' \
        -e 's|__xconfigfile__|xorg.conf|g' \
        -e 's|__projectroot__|$(prefix)|g' \
        -e 's|__apploaddir__|$(appdefaultdir)|' \
        -e 's|__appmansuffix__|$(APP_MAN_SUFFIX)|g' \
        -e 's|__libmansuffix__|$(LIB_MAN_SUFFIX)|g' \
        -e 's|__adminmansuffix__|$(ADMIN_MAN_SUFFIX)|g' \
        -e 's|__miscmansuffix__|$(MISC_MAN_SUFFIX)|g' \
        -e 's|__filemansuffix__|$(FILE_MAN_SUFFIX)|g'

SUFFIXES = .$(APP_MAN_SUFFIX) .man

.man.$(APP_MAN_SUFFIX):
	$(AM_V_GEN) $(SED) $(MAN_SUBSTS) < $< > $@

if LINT
ALL_LINT_FLAGS=$(LINT_FLAGS) $(DEFS) $(DEFAULT_INCLUDES) $(INCLUDES) \
                $(AM_CPPFLAGS) $(CPPFLAGS) $(AM_CFLAGS)

lint:
	$(LINT) $(ALL_LINT_FLAGS) $(constype_SOURCES)
endif LINT

else

all-local:
	@echo "constype not supported on this platform"

endif

EXTRA_DIST = constype.man ChangeLog autogen.sh
MAINTAINERCLEANFILES = ChangeLog

.PHONY: ChangeLog

ChangeLog:
	$(CHANGELOG_CMD)

dist-hook: ChangeLog
