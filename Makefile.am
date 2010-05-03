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

#(* $Id: Makefile.am,v 1.9 2010/03/10 14:32:55 remy Exp $ *)

SUBDIRS = src examples doc

if HAVE_FREETYPE
if HAVE_GIF
SUBDIRS += test
endif
endif

CVSRELEASETAG = Release-$(subst .,_,$(VERSION))
ANNOUNCEFILE  = Announce-$(VERSION)

WEBSITEDIR = /net/yquem/infosystems/www/bazaar/$(PACKAGE)
FTPSITEDIR = /net/yquem/infosystems/ftp/$(PACKAGE)
CVSROOTDIR = /net/yquem/devel/caml/repository/
CVSPKGDIR  = bazar-ocaml/$(PACKAGE)

cvstag:
	cvs tag -c $(CVSRELEASETAG)

cvsuntag:
	cvs tag -d $(CVSRELEASETAG)

announce:
	mail -n -s "New release $(VERSION) of $(NAME)" \
		caml-announce@inria.fr < $(ANNOUNCEFILE)

website: dist
	if [ -d $(WEBSITEDIR) ]; then     \
		: ; \
	else                              \
		$(INSTALL) -d -g caml -m 775 $(WEBSITEDIR); \
	fi
	$(INSTALL) -g caml -m 775 $(DIST_ARCHIVES) $(WEBSITEDIR)
	$(INSTALL) -g caml -m 775 doc/*.html $(WEBSITEDIR)
	$(INSTALL) -g caml -m 775 doc/*.jpg $(WEBSITEDIR)
	cd $(WEBSITEDIR) && ln -sf eng.html index.html

# ftpsite: dist
# 	if [ ! -d $(FTPSITEDIR) ]; then                     \
# 		$(INSTALL) -d -g caml -m g+w $(FTPSITEDIR); \
# 	done
# 	$(INSTALL) -g caml -m g+w $(DISTFILE) $(FTPSITEDIR)
