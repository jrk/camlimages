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

#(* $Id: Makefile.am,v 1.6 2007/02/20 21:19:05 rousse Exp $ *)

OCAMLSOURCES = guienv.ml usleep.ml gifanim.ml

noinst_PROGRAMS =
if BUILD_NATIVE
noinst_PROGRAMS += gifanim.opt
endif
if BUILD_BYTECODE
noinst_PROGRAMS += gifanim.byt
endif

gifanim_opt_SOURCES = $(OCAMLSOURCES)
gifanim_byt_SOURCES = $(OCAMLSOURCES)

OTHER_LIBS = unix.cma

include ../../Makefile.variables

all: byt opt

byt: gifanim.byt

opt: gifanim.opt

gifanim.byt$(EXEEXT): $(OCAMLBYTOBJS)
	$(OCAMLC) -o gifanim.byt$(EXEEXT) \
		$(DLLPATHS) $(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS) $(OCAMLBYTOBJS)

gifanim.opt$(EXEEXT): $(OCAMLOPTOBJS)
	$(OCAMLOPT) -o gifanim.opt$(EXEEXT) \
		$(LINKFLAGS) $(AM_LINKFLAGS) \
		$(OCAMLLIBS:.cma=.cmxa) $(OCAMLOPTOBJS)

include ../../Makefile.rules
