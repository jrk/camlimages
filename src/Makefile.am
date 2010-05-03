#*********************************************************************#
#                                                                     #
#                          Caml Images                                #
#                                                                     #
#            François Pessaux, projet Cristal, INRIA Rocquencourt     #
#            Pierre Weis, projet Cristal, INRIA Rocquencourt          #
#            Jun Furuse, projet Cristal, INRIA Rocquencourt           #
#                                                                     #
#  Copyright 1999-2004,                                               #
#  Institut National de Recherche en Informatique et en Automatique.  #
#  Distributed only by permission.                                    #
#                                                                     #
#*********************************************************************#

#(* $Id: Makefile.am,v 1.34 2009/07/04 03:38:36 furuse Exp $ *)

ocamlsitelibdir = $(OCAMLSITELIBDIR)
ocamlsitelib_DATA = camlimages.a \
		    camlimages_core.a \
		    libcamlimages.a \
		    libcamlimages_core.a \
		    $(OCAMLINTERFACES) \
		    $(OCAMLINTERFACES:.mli=.cmi) \
		    META
ocamlstublibdir = $(libdir)/ocaml/stublibs
ocamlstublib_DATA = dllcamlimages.so dllcamlimages_core.so

if BUILD_NATIVE
ocamlsitelib_DATA += camlimages.cmxa camlimages_core.cmxa
endif

if BUILD_BYTECODE
ocamlsitelib_DATA += camlimages.cma camlimages_core.cma
endif

BUILT_SOURCES = $(OCAMLBUILTSOURCES)

OCAMLCFLAGS	= -warn-error A -annot
LINKFLAGS	=	 
AM_OCAMLCFLAGS	=
AM_CFLAGS	= -I .. -DHAVE_CONFIG_H

# use two different variables here to avoid a circular dependency
# between Makefile and .depend file
OCAMLBUILTSOURCES = camlimages.ml
OCAMLSOURCES_CORE =	mstring.ml \
			color.ml \
			region.ml \
			tmpfile.ml \
			bitmap.ml \
			genimage.ml \
			rgba32.ml \
			rgb24.ml \
			index8.ml \
			index16.ml \
			cmyk32.ml \
			images.ml \
			oColor.ml \
			oImages.ml \
			reduce.ml \
			geometry.ml \
			colorhist.ml \
			blend.ml \
			bmp.ml \
			oBmp.ml \
			ppm.ml \
			oPpm.ml \
			xvthumb.ml \
			oXvthumb.ml \
			units.ml

OCAMLINTERFACES = info.mli \
		  mstring.mli \
		  color.mli \
		  region.mli \
		  tmpfile.mli \
		  bitmap.mli \
		  genimage.mli \
		  rgba32.mli \
		  rgb24.mli \
		  index8.mli \
		  index16.mli \
		  cmyk32.mli \
	  	  images.mli \
		  oColor.mli \
		  oImages.mli \
		  reduce.mli \
	 	  blend.mli \
		  bmp.mli \
	          ppm.mli \
	          xvthumb.mli \
	          oXvthumb.mli \
		  colorhist.mli \
		  geometry.mli 

CSOURCES_CORE = 

if HAVE_GIF
OCAMLSOURCES_CORE += 	gif.ml \
			oGif.ml
OCAMLINTERFACES += gif.mli
CSOURCES_CORE += gifread.c \
	    gifwrite.c
endif

if HAVE_PNG
OCAMLSOURCES_CORE += 	png.ml \
			oPng.ml
OCAMLINTERFACES += png.mli
CSOURCES_CORE += pngread.c \
	    pngwrite.c
endif

if HAVE_JPEG
OCAMLSOURCES_CORE += 	jpeg.ml \
			oJpeg.ml
OCAMLINTERFACES += jpeg.mli
CSOURCES_CORE += jpegread.c \
	    jpegwrite.c
endif

if HAVE_TIFF
OCAMLSOURCES_CORE += 	tiff.ml \
			oTiff.ml
OCAMLINTERFACES += tiff.mli
CSOURCES_CORE += tiffread.c \
	    tiffwrite.c
endif

if HAVE_XPM
OCAMLSOURCES_CORE += 	xpm.ml \
			oXpm.ml
OCAMLINTERFACES += xpm.mli
CSOURCES_CORE += xpmread.c \
	    xpmwrite.c
AM_CFLAGS += $(INCXPM)
endif

if HAVE_PS
OCAMLSOURCES_CORE += 	ps.ml \
			oPs.ml
OCAMLINTERFACES += ps.mli
endif

### end of core

OCAMLSOURCES= $(OCAMLSOURCES_CORE)
CSOURCES= $(CSOURCES_CORE)

OCAMLSOURCES += graphic_image.ml oGraphic.ml
OCAMLINTERFACES += graphic_image.mli

if HAVE_LABLGTK
OCAMLSOURCES += ximage.ml \
		oXimage.ml \
		imagegdk.ml
OCAMLINTERFACES += ximage.mli \
		   oXimage.mli \
		   imagegdk.mli
AM_OCAMLCFLAGS += -I $(LABLGTKDIR)
endif

if HAVE_LABLGTK2
OCAMLSOURCES += ximage2.ml \
		oXimage2.ml \
		imagegdk.ml
OCAMLINTERFACES += ximage2.mli \
		   oXimage2.mli \
		   imagegdk.mli
AM_OCAMLCFLAGS += -I $(LABLGTK2DIR)
endif

if HAVE_FREETYPE
OCAMLSOURCES += ftlow.ml \
		freetype.ml \
		jis_table.ml \
		jis_unicode.ml \
		fttext.ml \
		oFreetype.ml
OCAMLINTERFACES += ftlow.mli \
		   freetype.mli \
		   jis_unicode.mli \
		   fttext.mli
CSOURCES += ftintf.c
AM_CFLAGS += $(INCFREETYPE)
endif

ocamlsitelib_DATA += units.cmi oXpm.cmi
if HAVE_TIFF
ocamlsitelib_DATA += oTiff.cmi
endif
if HAVE_PS
ocamlsitelib_DATA += oPs.cmi
endif
ocamlsitelib_DATA += oPpm.cmi oPng.cmi oJpeg.cmi oGraphic.cmi
if HAVE_GIF
ocamlsitelib_DATA += oGif.cmi
endif
if HAVE_FREETYPE
ocamlsitelib_DATA += oFreetype.cmi
endif
ocamlsitelib_DATA += oBmp.cmi
if HAVE_FREETYPE
ocamlsitelib_DATA += jis_table.cmi
endif
ocamlsitelib_DATA += camlimages.cmi

EXTRA_DIST = $(OCAMLSOURCES) $(OCAMLINTERFACES) $(CSOURCES) camlimages.ml.in META.in

CLEANFILES = $(OCAMLBYTOBJS) \
	     $(OCAMLOPTOBJS) \
	     $(OCAMLOPTOBJS:.cmx=.o) \
	     $(OCAMLBUILTSOURCES:.ml=.cmi) \
	     $(OCAMLSOURCES:.ml=.cmi) \
	     info.cmi \
	     $(COBJS) \
	     libcamlimages.a \
	     dllcamlimages.so \
	     camlimages.cma \
	     camlimages.cmxa \
	     camlimages.a \
	     camlimages.ml \
	     META \
	     .depend

OCAMLBYTOBJS_CORE	= $(OCAMLBUILTSOURCES:.ml=.cmo) $(OCAMLSOURCES_CORE:.ml=.cmo)
OCAMLBYTOBJS	= $(OCAMLBUILTSOURCES:.ml=.cmo) $(OCAMLSOURCES:.ml=.cmo)
OCAMLOPTOBJS_CORE	= $(OCAMLBUILTSOURCES:.ml=.cmx) $(OCAMLSOURCES_CORE:.ml=.cmx)
OCAMLOPTOBJS	= $(OCAMLBUILTSOURCES:.ml=.cmx) $(OCAMLSOURCES:.ml=.cmx)
COBJS_CORE	= $(CSOURCES_CORE:.c=.o)
COBJS		= $(CSOURCES:.c=.o)
EXTCLIB_CORE	= $(LIBXPM) $(LIBTIFF) $(LIBPNG) $(LIBJPEG) $(LIBGIF)
EXTCLIB		= $(EXTCLIB_CORE) $(LIBFREETYPE) 

camlimages_core.a libcamlimages_core.a dllcamlimages_core.so: $(COBJS_CORE)
	$(OCAMLMKLIB) -o camlimages_core $(EXTCLIB_CORE) $(LDFLAGS) $(COBJS_CORE)

camlimages.a libcamlimages.a dllcamlimages.so: $(COBJS)
	$(OCAMLMKLIB) -o camlimages $(EXTCLIB) $(LDFLAGS) $(COBJS)


camlimages_core.cma: $(OCAMLBYTOBJS_CORE) camlimages_core.a dllcamlimages_core.so
	$(OCAMLMKLIB) -linkall -o camlimages_core $(EXTCLIB_CORE) $(LDFLAGS) $(OCAMLBYTOBJS_CORE)

camlimages.cma: $(OCAMLBYTOBJS) camlimages.a dllcamlimages.so
	$(OCAMLMKLIB) -linkall -o camlimages $(EXTCLIB) $(LDFLAGS) $(OCAMLBYTOBJS)

camlimages_core.cmxa: $(OCAMLOPTOBJS_CORE) camlimages_core.a dllcamlimages_core.so
	$(OCAMLMKLIB) -linkall -o camlimages_core $(EXTCLIB_CORE) $(LDFLAGS) $(OCAMLOPTOBJS_CORE)

camlimages.cmxa: $(OCAMLOPTOBJS) camlimages.a dllcamlimages.so
	$(OCAMLMKLIB) -linkall -o camlimages $(EXTCLIB) $(LDFLAGS) $(OCAMLOPTOBJS)

camlimages.ml: $(top_srcdir)/config.status camlimages.ml.in
	rm -f camlimages.ml camlimages.ml.tmp
	sed \
		-e 's,@VERSION\@,$(VERSION),g' \
		-e 's,@SUPPORT_GIF\@,$(SUPPORT_GIF),g' \
		-e 's,@SUPPORT_PNG\@,$(SUPPORT_PNG),g' \
		-e 's,@SUPPORT_JPEG\@,$(SUPPORT_JPEG),g' \
		-e 's,@SUPPORT_TIFF\@,$(SUPPORT_TIFF),g' \
		-e 's,@SUPPORT_FREETYPE\@,$(SUPPORT_FREETYPE),g' \
		-e 's,@SUPPORT_PS\@,$(SUPPORT_PS),g' \
		-e 's,@SUPPORT_XPM\@,$(SUPPORT_XPM),g' \
		-e 's,@PATH_RGB_TXT\@,$(PATH_RGB_TXT),g' \
		-e 's,@GS\@,$(GS),g' \
		-e 's,@WORD_SIZE\@,$(WORD_SIZE),g' \
		$(srcdir)/camlimages.ml.in > camlimages.ml.tmp
	mv camlimages.ml.tmp camlimages.ml

top: all
	$(OCAMLMKTOP) -custom -o customtop -ccopt "-L." \
		$(WITH_UNIX) \
		$(WITH_CAMLIMAGES)

include ../Makefile.rules
