# For license: see LICENSE file at top-level

SHMEM_HDRS             =  shmem/defs.h \
				shmem/depr.h \
				shmem/cache.h \
				shmem/api.h \
				shmem.h



#
# deprecated locations of files from earlier specs.  Always required.
#
SHMEM_HDRS             += mpp/shmem.h mpp/shmemx.h


#
# must install if fortran requested
#
if ENABLE_FORTRAN
SHMEM_HDRS             += shmem/defs.fh shmem.fh
SHMEM_HDRS             += mpp/shmem.fh mpp/shmemx.fh
endif # fortran


#
# extensions, maybe for fortran too
#
if ENABLE_EXPERIMENTAL

if ENABLE_PSHMEM
SHMEM_HDRS             += pshmemx.h
endif # pshmem

if ENABLE_FORTRAN
SHMEM_HDRS             += pshmemx.fh
endif # fortran

endif # experimental



#
# add profiling interface if requested
#
if ENABLE_PSHMEM
SHMEM_HDRS             += pshmem.h

if ENABLE_FORTRAN
SHMEM_HDRS             += pshmem.fh
endif # fortran

endif # pshmem


#
# need presence of shmemx header file whether features requested or not.
# Also add fortran one if enabled.
#
if ENABLE_EXPERIMENTAL
SHMEMX_HEADER           = shmemx.h
SHMEMX_HEADER_F         = shmemx.fh
else
SHMEMX_HEADER           = null-shmemx.h
SHMEMX_HEADER_F         = null-shmemx.fh
endif # experimental


# retain tree
nobase_include_HEADERS  = $(SHMEM_HDRS)

install-data-hook:
	cp -p $(SHMEMX_HEADER) $(includedir)/shmemx.h
	cp -p $(SHMEMX_HEADER_F) $(includedir)/shmemx.fh
