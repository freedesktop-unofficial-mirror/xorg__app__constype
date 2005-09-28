# $Id$
#
# Copyright 2005 Sun Microsystems, Inc.  All rights reserved.
# 
# Permission is hereby granted, free of charge, to any person obtaining a
# copy of this software and associated documentation files (the
# "Software"), to deal in the Software without restriction, including
# without limitation the rights to use, copy, modify, merge, publish,
# distribute, and/or sell copies of the Software, and to permit persons
# to whom the Software is furnished to do so, provided that the above
# copyright notice(s) and this permission notice appear in all copies of
# the Software and that both the above copyright notice(s) and this
# permission notice appear in supporting documentation.
# 
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
# OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
# MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT
# OF THIRD PARTY RIGHTS. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR
# HOLDERS INCLUDED IN THIS NOTICE BE LIABLE FOR ANY CLAIM, OR ANY SPECIAL
# INDIRECT OR CONSEQUENTIAL DAMAGES, OR ANY DAMAGES WHATSOEVER RESULTING
# FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT,
# NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION
# WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
# 
# Except as contained in this notice, the name of a copyright holder
# shall not be used in advertising or otherwise to promote the sale, use
# or other dealings in this Software without prior written authorization
# of the copyright holder.
# 

if BUILD_CONSTYPE

bin_PROGRAMS = constype

constype_SOURCES = constype.c

EXTRA_DIST = constype.man

man1_MANS = constype.1

CLEANFILES = $(man1_MANS)

all-local: $(man1_MANS)

# Rules for generating files using the C pre-processor
# (Replaces CppFileTarget from Imake)

SED = sed

SUFFIXES = .1 .man

# Delete line numbers from the cpp output (-P is not portable, I guess).

CPP_SED_MAGIC = $(SED) -e '/^\#  *[0-9][0-9]*  *.*$$/d' \
                       -e '/^\#line  *[0-9][0-9]*  *.*$$/d'

XORGRELSTRING = @PACKAGE_STRING@
  XORGMANNAME = X Version 11

CPP_FILES_FLAGS = -D__xorgversion__="\"$(XORGRELSTRING)\" \"$(XORGMANNAME)\""

.man.1:
	$(RAWCPP) $(RAWCPPFLAGS) $(CPP_FILES_FLAGS) < $< | $(CPP_SED_MAGIC) > $@

else

all-local:
	@echo "constype not supported on this platform"

endif