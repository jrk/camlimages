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

OCAMLSOURCES = imgstat.ml

noinst_PROGRAMS =
if BUILD_NATIVE
noinst_PROGRAMS += imgstat.opt
endif
if BUILD_BYTECODE
noinst_PROGRAMS += imgstat.byt
endif

imgstat_opt_SOURCES = $(OCAMLSOURCES)
imgstat_byt_SOURCES = $(OCAMLSOURCES)

include ../../Makefile.variables

imgstat.byt$(EXEEXT): $(OCAMLBYTOBJS)
	$(OCAMLC) -o imgstat.byt$(EXEEXT) \
		$(DLLPATHS) $(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS_CORE) $(OCAMLBYTOBJS)

imgstat.opt$(EXEEXT): $(OCAMLOPTOBJS)
	$(OCAMLOPT) -o imgstat.opt$(EXEEXT) \
		$(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS_CORE:.cma=.cmxa) $(OCAMLOPTOBJS)

include ../../Makefile.rules
