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

#(* $Id: Makefile.am,v 1.2 2007/01/08 14:04:48 rousse Exp $ *)

SUBDIRS = crop normalize converter edgedetect imgstat monochrome resize

if HAVE_LABLGTK
if HAVE_GIF
SUBDIRS += gifanim
endif
endif

if HAVE_LABLGTK2
if HAVE_JPEG
SUBDIRS += liv
endif
endif

if HAVE_FREETYPE
SUBDIRS += ttfimg
endif

if HAVE_TIFF
SUBDIRS += tiffps
endif
