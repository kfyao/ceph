libperfglue_la_SOURCES =

if WITH_TCMALLOC
libperfglue_la_SOURCES += perfglue/heap_profiler.cc
AM_CFLAGS += -fno-builtin-malloc -fno-builtin-calloc -fno-builtin-realloc -fno-builtin-free
AM_CXXFLAGS += -fno-builtin-malloc -fno-builtin-calloc -fno-builtin-realloc -fno-builtin-free
else
libperfglue_la_SOURCES += perfglue/disabled_heap_profiler.cc
endif # WITH_TCMALLOC

if WITH_PROFILER
libperfglue_la_SOURCES += perfglue/cpu_profiler.cc
else
libperfglue_la_SOURCES += perfglue/disabled_stubs.cc
endif # WITH_PROFILER

libperfglue_la_LIBADD = -ltcmalloc
noinst_LTLIBRARIES += libperfglue.la

noinst_HEADERS += \
	perfglue/cpu_profiler.h \
	perfglue/heap_profiler.h

