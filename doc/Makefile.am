#*********************************************************************#
#                                                                     #
#                          Caml Images                                #
#                                                                     #
#            Pierre Weis, projet Cristal, INRIA Rocquencourt          #
#                                                                     #
#  Copyright 2004 Institut National de Recherche en Informatique et   #
#  en Automatique.  Distributed only by permission.                   #
#                                                                     #
#*********************************************************************#

#(* $Id: Makefile.am,v 1.2 2007/01/08 16:44:30 rousse Exp $ *)

noinst_DATA = eng.html

CLEANFILES = eng.html

EXTRA_DIST = eng.html.in \
	     crop-icon.jpg \
	     crop.jpg \
	     edge-icon.jpg \
	     edge.jpg \
	     fumicaml2-small.jpg \
	     lvdemo-icon.jpg \
	     lvdemo.jpg \
	     test.jpg \
	     test-small.jpg \
	     ttfimg-icon.jpg \
	     ttfimg.jpg

eng.html: $(top_srcdir)/config.status eng.html.in
	rm -f eng.html eng.html.tmp
	sed \
		-e 's,@VERSION\@,$(VERSION),g' \
		$(srcdir)/eng.html.in > eng.html.tmp
	mv eng.html.tmp eng.html
