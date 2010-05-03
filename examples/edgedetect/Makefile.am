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

OCAMLSOURCES = edge.ml

noinst_PROGRAMS =
if BUILD_NATIVE
noinst_PROGRAMS += edge.opt
endif
if BUILD_BYTECODE
noinst_PROGRAMS += edge.byt
endif

edge_opt_SOURCES = $(OCAMLSOURCES)
edge_byt_SOURCES = $(OCAMLSOURCES)

include ../../Makefile.variables

edge.byt$(EXEEXT): $(OCAMLBYTOBJS)
	$(OCAMLC) -o edge.byt$(EXEEXT) \
		$(DLLPATHS) $(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS_CORE) $(OCAMLBYTOBJS)

edge.opt$(EXEEXT): $(OCAMLOPTOBJS)
	$(OCAMLOPT) -o edge.opt$(EXEEXT) \
		$(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS_CORE:.cma=.cmxa) $(OCAMLOPTOBJS)

include ../../Makefile.rules
