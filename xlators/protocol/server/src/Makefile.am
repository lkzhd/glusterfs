xlator_LTLIBRARIES = server.la
xlatordir = $(libdir)/glusterfs/$(PACKAGE_VERSION)/xlator/protocol

server_la_LDFLAGS = $(GF_XLATOR_DEFAULT_LDFLAGS)

server_la_LIBADD = $(top_builddir)/libglusterfs/src/libglusterfs.la \
	$(top_builddir)/rpc/rpc-lib/src/libgfrpc.la \
	$(top_builddir)/rpc/xdr/src/libgfxdr.la

server_la_SOURCES = server.c server-resolve.c server-helpers.c  \
	server-rpc-fops.c server-handshake.c authenticate.c

noinst_HEADERS = server.h server-helpers.h server-mem-types.h authenticate.h \
	server-messages.h

AM_CPPFLAGS = $(GF_CPPFLAGS) \
	-I$(top_srcdir)/libglusterfs/src \
	-DCONFDIR=\"$(sysconfdir)/glusterfs\" \
	-DLIBDIR=\"$(libdir)/glusterfs/$(PACKAGE_VERSION)/auth\" \
	-I$(top_srcdir)/xlators/protocol/lib/src \
	-I$(top_srcdir)/rpc/rpc-lib/src \
	-I$(top_srcdir)/rpc/xdr/src

AM_CFLAGS = -Wall $(GF_CFLAGS) \
            -DDATADIR=\"$(localstatedir)\"

CLEANFILES = *~
