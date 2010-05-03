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

#(* $Id: Makefile.am,v 1.9 2008/06/16 22:35:41 furuse Exp $ *)

OCAMLSOURCES = deficon.ml \
	       mylazy.ml \
	       cache.ml \
	       livmisc.ml \
	       gui.ml \
	       jWidget.ml \
	       seq.ml \
	       tout.ml \
	       enhance.ml \
	       display.ml \
	       viewer.ml \
	       edge.ml \
	       pathfind.ml \
	       iconcap.ml \
	       livshtype.ml \
	       icon.ml \
	       livsh.ml \
	       scandir.ml \
	       jpf.ml \
	       liv.ml

noinst_PROGRAMS =
if BUILD_NATIVE
noinst_PROGRAMS += liv.opt
endif
if BUILD_BYTECODE
noinst_PROGRAMS += liv.byt
endif

liv_opt_SOURCES = $(OCAMLSOURCES)
liv_byt_SOURCES = $(OCAMLSOURCES)

OTHER_LIBS = unix.cma

include ../../Makefile.variables

EXTRA_DIST = BulletHole.xpm \
	     faceanm.gif \
	     FilesLink.xpm \
	     FileUnknown.xpm \
	     File.xpm \
	     FolderLink.xpm \
	     Folder.xpm \
	     livdemo.jpg \
	     Monalisa.xpm \
	     sound.xpm

all: liv.byt$(EXEEXT)
opt: liv.opt$(EXEEXT)

liv.byt$(EXEEXT): $(OCAMLBYTOBJS)
	$(OCAMLC) -o liv.byt$(EXEEXT) \
		$(DLLPATHS) $(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS) $(OCAMLBYTOBJS)

liv.opt$(EXEEXT): $(OCAMLOPTOBJS)
	$(OCAMLOPT) -o liv.opt$(EXEEXT) \
		$(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS:.cma=.cmxa) $(OCAMLOPTOBJS)

include ../../Makefile.rules
