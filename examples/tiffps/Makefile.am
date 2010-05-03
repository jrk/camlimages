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

#(* $Id: Makefile.am,v 1.7 2007/02/20 21:19:11 rousse Exp $ *)

OCAMLSOURCES = tiffps.ml

noinst_PROGRAMS =
if BUILD_NATIVE
noinst_PROGRAMS += tiffps.opt
endif
if BUILD_BYTECODE
noinst_PROGRAMS += tiffps.byt
endif

tiffps_opt_SOURCES = $(OCAMLSOURCES)
tiffps_byt_SOURCES = $(OCAMLSOURCES)

include ../../Makefile.variables

tiffps.byt$(EXEEXT): $(OCAMLBYTOBJS)
	$(OCAMLC) -o tiffps.byt$(EXEEXT) \
		$(DLLPATHS) $(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS) $(OCAMLBYTOBJS)

tiffps.opt$(EXEEXT): $(OCAMLOPTOBJS)
	$(OCAMLOPT) -o tiffps.opt$(EXEEXT) \
		$(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS:.cma=.cmxa) $(OCAMLOPTOBJS)

include ../../Makefile.rules
