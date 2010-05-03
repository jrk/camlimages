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

#(* $Id: Makefile.am,v 1.6 2007/02/20 21:19:22 rousse Exp $ *)

OCAMLSOURCES = test.ml

TESTS =
check_PROGRAMS =
if BUILD_NATIVE
check_PROGRAMS += test.opt
TESTS += test.opts
endif
if BUILD_BYTECODE
check_PROGRAMS += test.byt
TESTS += test.byt
endif

test_opt_SOURCES = $(OCAMLSOURCES)
test_byt_SOURCES = $(OCAMLSOURCES)

include ../Makefile.variables

EXTRA_DIST = images micap.ttf

CLEANFILES += out.image

test.byt$(EXEEXT): $(OCAMLBYTOBJS)
	$(OCAMLC) -o test.byt$(EXEEXT) \
		$(DLLPATHS) $(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS) $(OCAMLBYTOBJS)

test.opt$(EXEEXT): $(OCAMLOPTOBJS)
	$(OCAMLOPT) -o test.opt$(EXEEXT) \
		$(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS:.cma=.cmxa) $(OCAMLOPTOBJS)

dist-hook:
	rm -rf $(distdir)/images/CVS
	rm -f $(distdir)/images/.cvsignore


include ../Makefile.rules
