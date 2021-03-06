#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL)". You may
# only use this file in accordance with the terms of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source. A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2015 Alexander Pyhalov
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		gtkimageview
COMPONENT_VERSION=	1.6.4
COMPONENT_REVISON=	3
COMPONENT_PROJECT_URL=	http://trac.bjourne.webfactional.com
COMPONENT_SUMMARY=	A simple image viewer widget for GTK+
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	\
    sha256:67e4c734be69c879101e62ba8573b17b80396ff21e83392d2f7b5af30bf4c3c5
# trac.bjourne.webfactional.com is dead
COMPONENT_ARCHIVE_URL=	http://dlc.openindiana.org/oi/jds/downloads/sources/$(COMPONENT_ARCHIVE)
COMPONENT_LICENSE=	LGPLv2.1
COMPONENT_LICENSE_FILE=	COPYING
COMPONENT_CLASSIFICATION=	Desktop (GNOME)/Libraries
COMPONENT_FMRI= 	library/desktop/gtkimageview

include $(WS_MAKE_RULES)/prep.mk
include $(WS_MAKE_RULES)/configure.mk
include $(WS_MAKE_RULES)/ips.mk

PATH=$(PATH.gnu)

CFLAGS+=-Wno-deprecated-declarations

COMPONENT_PREP_ACTION =        ( cp files/* $(@D)/src && cd $(@D)  && \
					libtoolize --copy --force &&\
					aclocal -I . &&\
					automake -c -f -a &&\
					autoconf )

# Missing files in build dir for configure without this.
COMPONENT_PRE_CONFIGURE_ACTION =        ($(CLONEY) $(SOURCE_DIR) $(@D))


CONFIGURE_OPTIONS+=	--sysconfdir=/etc
CONFIGURE_OPTIONS+=	--enable-compile-warnings=no
CONFIGURE_OPTIONS+=	--disable-gtk-doc
CONFIGURE_OPTIONS+=	--disable-static

CFLAGS += -D__EXTENSIONS__

# common targets
build:		$(BUILD_32_and_64)

install:	$(INSTALL_32_and_64)

test:		$(NO_TESTS)

# Auto-generated dependencies
REQUIRED_PACKAGES += library/desktop/gdk-pixbuf
REQUIRED_PACKAGES += library/desktop/gtk2
REQUIRED_PACKAGES += library/glib2
REQUIRED_PACKAGES += system/library
