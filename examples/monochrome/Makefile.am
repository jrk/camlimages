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

#(* $Id: Makefile.am,v 1.7 2008/02/17 23:24:16 furuse Exp $ *)

OCAMLSOURCES = monochrome.ml

noinst_PROGRAMS =
if BUILD_NATIVE
noinst_PROGRAMS += monochrome.opt
endif
if BUILD_BYTECODE
noinst_PROGRAMS += monochrome.byt
endif

monochrome_opt_SOURCES = $(OCAMLSOURCES)
monochrome_byt_SOURCES = $(OCAMLSOURCES)

include ../../Makefile.variables

monochrome.byt$(EXEEXT): $(OCAMLBYTOBJS)
	$(OCAMLC) -o monochrome.byt$(EXEEXT) \
		$(DLLPATHS) $(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS_CORE) $(OCAMLBYTOBJS)

monochrome.opt$(EXEEXT): $(OCAMLOPTOBJS)
	$(OCAMLOPT) -o monochrome.opt$(EXEEXT) \
		$(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS_CORE:.cma=.cmxa) $(OCAMLOPTOBJS)

include ../../Makefile.rules
