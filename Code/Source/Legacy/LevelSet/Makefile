# Hey emacs, this is a -*- makefile -*-

# Copyright (c) 2009-2011 Open Source Medical Software Corporation,
#                         University of California, San Diego.
#
# All rights reserved.
#
# Portions copyright (c) 1999-2007 Stanford University,
# Nathan Wilson, Ken Wang, Charles Taylor.
#
# See SimVascular Acknowledgements file for additional
# contributors to the source code.
#
# Permission is hereby granted, free of charge, to any person obtaining
# a copy of this software and associated documentation files (the
# "Software"), to deal in the Software without restriction, including
# without limitation the rights to use, copy, modify, merge, publish,
# distribute, sublicense, and/or sell copies of the Software, and to
# permit persons to whom the Software is furnished to do so, subject
# to the following conditions:
#
# The above copyright notice and this permission notice shall be included
# in all copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
# OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
# MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
# IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
# CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
# TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
# SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

TOP=../../../../BuildWithMake

include $(TOP)/include.mk

# --------------
# Compiler flags
# --------------

CXXFLAGS = $(GLOBAL_CXXFLAGS) $(LOCAL_INCDIR) $(TCLTK_INCDIR) \
	   $(VTK_INCDIRS)

CREATE_EXPORTS_CV_ALL_CAPS=SV_LSET
CREATE_EXPORTS_CV_EXPORT_NAME=SV_EXPORT_LSET
CREATE_EXPORTS_CV_FILE_H=svLSetExports.h

CXXFLAGS += -DSV_EXPORT_LSET_COMPILE

HDRS	= cvLevelSet.h cvLevelSetNode.h \
	  cvLevelSetStructuredGrid.h cvLevelSetDenseGrid.h \
          cvLevelSetSparseGrid.h

HDRS   += cvLevelSetVelocity.h cvLevelSetVelocityKGI.h \
          cvLevelSetVelocityConstant.h \
	  cvLevelSetVelocityThreshold.h cvLevelSetVelocityPotential.h \
          cvLevelSetVelocityExponentialDecay.h cvLevelSetVelocitySmooth.h \
          cvLevelSetVelocityImage.h

CXXSRCS	= cvLevelSet.cxx cvLevelSetNode.cxx \
	  cvLevelSetStructuredGrid.cxx cvLevelSetDenseGrid.cxx \
          cvLevelSetSparseGrid.cxx

CXXSRCS += cvLevelSetVelocity.cxx cvLevelSetVelocityKGI.cxx \
          cvLevelSetVelocityConstant.cxx \
	  cvLevelSetVelocityThreshold.cxx cvLevelSetVelocityPotential.cxx \
          cvLevelSetVelocityExponentialDecay.cxx \
          cvLevelSetVelocitySmooth.cxx cvLevelSetVelocityImage.cxx

DLLHDRS = cv_LsetCore_init.h cv_LsetV_init.h cv_Lset_init.h
DLLSRCS = cv_LsetCore_init.cxx cv_LsetV_init.cxx cv_Lset_init.cxx

# -------
# Targets
# -------

TARGET_LIB_NAME = $(SV_LIB_LSET_NAME)

DLLLIBS = $(SVLIBFLAG)$(SV_LIB_IMAGE_NAME)$(LIBLINKEXT) \
	  $(SVLIBFLAG)$(SV_LIB_SOLID_NAME)$(LIBLINKEXT) \
	  $(SVLIBFLAG)$(SV_LIB_GEOM_NAME)$(LIBLINKEXT) \
          $(SVLIBFLAG)$(SV_LIB_REPOSITORY_NAME)$(LIBLINKEXT) \
          $(SVLIBFLAG)$(SV_LIB_UTILS_NAME)$(LIBLINKEXT) \
	  $(VMTK_LIBS)

include $(TOP)/targetlib.mk

