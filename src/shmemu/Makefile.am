# For license: see LICENSE file at top-level

OTHER_CPPFLAGS            = -I../../include \
				-I$(srcdir)/../shmemc \
				-I$(srcdir)/uthash
LIBSHMEMU_SOURCES         = hostname.c fatal.c logger.c timer.c unitparse.c \
				shmemu-init.c miscops.c round.c

if ENABLE_DEBUG
LIBSHMEMU_SOURCES        += deprecate.c
endif

lib_LTLIBRARIES           = libshmemu.la
libshmemu_la_SOURCES      = $(LIBSHMEMU_SOURCES)
libshmemu_la_CFLAGS       = $(OTHER_CPPFLAGS)

lib_LIBRARIES             = libshmemu.a
libshmemu_a_SOURCES       = $(LIBSHMEMU_SOURCES)
libshmemu_a_CFLAGS        = $(OTHER_CPPFLAGS)
