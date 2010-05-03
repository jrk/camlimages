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

#(* $Id: Makefile.am,v 1.7 2008/02/17 23:24:15 furuse Exp $ *)

OCAMLSOURCES = crop.ml

noinst_PROGRAMS =
if BUILD_NATIVE
noinst_PROGRAMS += crop.opt
endif
if BUILD_BYTECODE
noinst_PROGRAMS += crop.byt
endif

crop_opt_SOURCES = $(OCAMLSOURCES)
crop_byt_SOURCES = $(OCAMLSOURCES)

OTHER_LIBS = unix.cma

include ../../Makefile.variables

crop.byt$(EXEEXT): $(OCAMLBYTOBJS)
	$(OCAMLC) -o crop.byt$(EXEEXT) \
		$(DLLPATHS) $(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS_CORE) $(OCAMLBYTOBJS)

crop.opt$(EXEEXT): $(OCAMLOPTOBJS)
	$(OCAMLOPT) -o crop.opt$(EXEEXT) \
		$(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS_CORE:.cma=.cmxa) $(OCAMLOPTOBJS)

include ../../Makefile.rules
