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

#(* $Id: Makefile.am,v 1.8 2008/02/17 23:24:16 furuse Exp $ *)

OCAMLSOURCES = normalize.ml

noinst_PROGRAMS =
if BUILD_NATIVE
noinst_PROGRAMS += normalize.opt
endif
if BUILD_BYTECODE
noinst_PROGRAMS += normalize.byt
endif

normalize_opt_SOURCES = $(OCAMLSOURCES)
normalize_byt_SOURCES = $(OCAMLSOURCES)

include ../../Makefile.variables

normalize.byt$(EXEEXT): $(OCAMLBYTOBJS)
	$(OCAMLC) -o normalize.byt$(EXEEXT) \
		$(DLLPATHS) $(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS_CORE) $(OCAMLBYTOBJS)

normalize.opt$(EXEEXT): $(OCAMLOPTOBJS)
	$(OCAMLOPT) -o normalize.opt$(EXEEXT) \
		$(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS_CORE:.cma=.cmxa) $(OCAMLOPTOBJS)

include ../../Makefile.rules
