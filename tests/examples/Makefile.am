if USE_UVCH264
UVCH264_DIR=uvch264
else
UVCH264_DIR=
endif

if HAVE_GTK
GTK_EXAMPLES=mxf camerabin2 $(UVCH264_DIR)
else
GTK_EXAMPLES=
endif

if USE_DIRECTFB
DIRECTFB_DIR=directfb
else
DIRECTFB_DIR=
endif

OPENCV_EXAMPLES=opencv

if USE_OPENGL
GL_DIR=gl
else
GL_DIR=
endif

if HAVE_AVFOUNDATION
if HAVE_IOS
AVSAMPLE_DIR=
else
AVSAMPLE_DIR=avsamplesink
endif
else
AVSAMPLE_DIR=
endif

if USE_GTK3
GTK3_DIR=gtk
else
GTK3_DIR=
endif

noinst_PROGRAMS = playout

playout_SOURCES = playout.c
playout_CFLAGS = $(GST_PLUGINS_BASE_CFLAGS) $(GST_CFLAGS)
playout_LDADD = $(GST_PLUGINS_BASE_LIBS) -lgstvideo-$(GST_API_VERSION) $(GST_LIBS)

SUBDIRS= codecparsers mpegts $(DIRECTFB_DIR) $(GTK_EXAMPLES) $(OPENCV_EXAMPLES) \
        $(GL_DIR) $(GTK3_DIR) $(AVSAMPLE_DIR)
DIST_SUBDIRS= codecparsers mpegts camerabin2 directfb mxf opencv uvch264 gl gtk avsamplesink

if USE_WAYLAND
WAYLAND_DIR=wayland
else
WAYLAND_DIR=
endif

SUBDIRS= mpegts $(DIRECTFB_DIR) $(GTK_EXAMPLES) $(OPENCV_EXAMPLES) $(GL_DIR) \
	$(WAYLAND_DIR)
DIST_SUBDIRS= mpegts camerabin2 directfb mxf opencv uvch264 gl wayland

include $(top_srcdir)/common/parallel-subdirs.mak
