#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#

#
# Copyright (c) 2011, 2013, Oracle and/or its affiliates. All rights reserved.
# Copyright (c) 2013, Alexander Pyhalov. All rights reserved.
#

BUILD_STYLE=makemaker
BUILD_BITS=32_and_64
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME= 	DBI-PostgreSQL
COMPONENT_VERSION=	3.10.0
COMPONENT_SUMMARY= 	The DBI PostgreSQL Interface for Perl
COMPONENT_SRC=		DBD-Pg-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= \
  sha256:e103268a63e2828e3d43659bdba5f743446cbbe047a766f843112eedae105f80
COMPONENT_ARCHIVE_URL= \
  http://search.cpan.org/CPAN/authors/id/T/TU/TURNSTEP/$(COMPONENT_ARCHIVE)
COMPONENT_PROJECT_URL = http://search.cpan.org/dist/DBD-Pg/Pg.pm

# Don't depend on host default pg_config
PATH=$(PG_BINDIR):/usr/sbin:/usr/bin:/usr/perl5/bin

TEST_TARGET=$(NO_TESTS)
include $(WS_MAKE_RULES)/common.mk

LD_OPTIONS += -L$(PG_LIBDIR) -R$(PG_LIBDIR)

# Build dependencies
REQUIRED_PACKAGES += $(PG_DEVELOPER_PKG)
REQUIRED_PACKAGES += library/perl-5/database
# Auto-generated dependencies
REQUIRED_PACKAGES += $(GXX_RUNTIME_PKG)
REQUIRED_PACKAGES += $(PG_LIBRARY_PKG)
REQUIRED_PACKAGES += system/library
