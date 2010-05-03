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

#(* $Id: Makefile.am,v 1.6 2007/02/20 21:19:15 rousse Exp $ *)

OCAMLSOURCES = ttfimg.ml

noinst_PROGRAMS =
if BUILD_NATIVE
noinst_PROGRAMS += ttfimg.opt
endif
if BUILD_BYTECODE
noinst_PROGRAMS += ttfimg.byt
endif

ttfimg_opt_SOURCES = $(OCAMLSOURCES)
ttfimg_byt_SOURCES = $(OCAMLSOURCES)

include ../../Makefile.variables

ttfimg.byt$(EXEEXT): $(OCAMLBYTOBJS)
	$(OCAMLC) -o ttfimg.byt$(EXEEXT) \
		$(DLLPATHS) $(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS) $(OCAMLBYTOBJS)

ttfimg.opt$(EXEEXT): $(OCAMLOPTOBJS)
	$(OCAMLOPT) -o ttfimg.opt$(EXEEXT) \
		$(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS:.cma=.cmxa) $(OCAMLOPTOBJS)

include ../../Makefile.rules
