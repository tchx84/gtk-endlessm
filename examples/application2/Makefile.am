GTK_CFLAGS =	 				\
	-I$(top_srcdir)				\
	$(GTK_DEP_CFLAGS)

GTK_LIBS = 					\
        $(top_builddir)/gtk/libgtk-3.la 	\
        $(top_builddir)/gdk/libgdk-3.la 	\
        $(GTK_DEP_LIBS)


noinst_PROGRAMS = exampleapp

exampleapp_CFLAGS = $(GTK_CFLAGS)
exampleapp_LDADD = $(GTK_LIBS)
exampleapp_SOURCES = 				\
	main.c 					\
	exampleapp.c exampleapp.h 		\
	exampleappwin.c exampleappwin.h
nodist_exampleapp_SOURCES =			\
	resources.c

BUILT_SOURCES = $(nodist_exampleapp_SOURCES)

resources.c: exampleapp.gresource.xml window.ui
	$(AM_V_GEN) $(GLIB_COMPILE_RESOURCES) $(srcdir)/exampleapp.gresource.xml \
		--target=$@ --sourcedir=$(srcdir) --generate-source

EXTRA_DIST = 					\
	window.ui 				\
	exampleapp.gresource.xml	\
	meson.build

CLEANFILES = $(BUILT_SOURCES)

-include $(top_srcdir)/git.mk
