plugin_LTLIBRARIES = libgstmmal.la

libgstmmal_la_SOURCES = \
	../ext/mmal/mmal_buffer_workaround.c \
	gstmmal.c \
	gstmmalclock.c \
	gstmmalutil.c \
	gstmmalmemory.c \
	gstmmalh264dec.c \
	gstmmalmpegviddec.c \
	gstmmalvideodec.c \
	gstmmalvideosink.c \
	gstmmalwmvdec.c \
	gstmmalvp6dec.c \
	gstmmalvp8dec.c \
	gstmmaldeinterlace.c

noinst_HEADERS = \
	gstmmalclock.h \
	gstmmalutil.h \
	gstmmalmemory.h \
	gstmmalh264dec.h \
	gstmmalmpegviddec.h \
	gstmmalvideodec.h \
	gstmmalvideosink.h \
	gstmmalwmvdec.h \
	gstmmalvp6dec.h \
	gstmmalvp8dec.h \
	gstmmaldeinterlace.h \
	gstmmalglupload.h

# N.B. the `-fgnu89-inline` is there to suppress annoying "inline function
# declared but never defined" warning from VC headers.
#
libgstmmal_la_CFLAGS = \
	$(AM_CFLAGS) \
	$(GST_PLUGINS_BASE_CFLAGS) \
	$(GST_BASE_CFLAGS) \
	$(GST_CFLAGS) \
	$(GMODULE_NO_EXPORT_CFLAGS) \
	-fgnu89-inline \
	-Wl,--no-as-needed -Wl,-lmmal

libgstmmal_la_LIBADD = \
	-lbcm_host \
	-lmmal \
	$(GST_PLUGINS_BASE_LIBS) \
	-lgstaudio-@GST_API_VERSION@ \
	-lgstpbutils-@GST_API_VERSION@ \
	-lgstvideo-@GST_API_VERSION@ \
	$(GST_BASE_LIBS) \
	$(GST_LIBS) \
	$(GMODULE_NO_EXPORT_LIBS)

libgstmmal_la_LDFLAGS = $(GST_PLUGIN_LDFLAGS)

if HAVE_GST_GL
libgstmmal_la_SOURCES += gstmmalglupload.c
libgstmmal_la_CFLAGS += $(GST_GL_CFLAGS) -DENABLE_MMALGLUPLOAD=1
libgstmmal_la_LIBADD += $(GST_GL_LIBS)
endif

EXTRA_DIST =
