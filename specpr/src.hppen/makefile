#
#	@(#)makefile	2.4	02/07/89	09:37:25
#	makefile for hp pen plotter spooler filter
#	J.A.Hoover	initial version 5/16/84
#
#       02/23/2002 Randall Dailey
#          Modified to remove references to SCCS
SRC=	\
finishplt.c	\
finishup.c	\
greek.c	\
hpdaemon.c	\
initpltr.c	\
initport.c	\
logerr.c	\
openargs.c	\
pagefeed.c	\
plotem.c

OBJ=	\
finishplt.o	\
finishup.o	\
greek.o	\
hpdaemon.o	\
initpltr.o	\
initport.o	\
logerr.o	\
openargs.o	\
pagefeed.o	\
plotem.o

OBJ2=	\
finishplt.o	\
finishup.o	\
greek.o	\
hpdaemon.o	\
initpltr2.o	\
initport2.o	\
logerr.o	\
openargs.o	\
pagefeed.o	\
plotem.o

HDR=hpdaemon.h 

CUTTER=CUTTER
CMODE=RS232
LPR=vcat
SHELL=/bin/sh

hpdaemon:	$(HDR) $(OBJ)
	cc $(CFLAGS) -o hpdaemon $(OBJ) -lm $(LSTRING)

hpdaemon2:	$(HDR) $(OBJ2)
	cc $(CFLAGS) -o hpdaemon2 $(OBJ2) -lm $(LSTRING)

initport.o:	initport.c
	cc $(CFLAGS) -DPLOTTER -D$(CMODE) -D$(CUTTER) -c -o initport.o initport.c

initport2.o:	initport.c
	cc $(CFLAGS) -DPLOTTER2 -D$(CMODE) -D$(CUTTER) -c -o initport2.o initport.c

initpltr.o:	initpltr.c
	cc $(CFLAGS) -DPLOTTER -D$(CMODE) -D$(CUTTER) -c -o initpltr.o initpltr.c

initpltr2.o:	initpltr.c
	cc $(CFLAGS) -DPLOTTER2 -D$(CMODE) -D$(CUTTER) -c -o initpltr2.o initpltr.c

finishplt.o:	finishplt.c
	cc  $(CFLAGS) -D$(CMODE) -D$(CUTTER) -c -o finishplt.o finishplt.c

finishup.o:	finishup.c
	cc $(CFLAGS) -D$(CMODE) -D$(CUTTER) -c -o finishup.o finishup.c

greek.o:	greek.c
	cc $(CFLAGS) -D$(CMODE) -D$(CUTTER) -c -o greek.o greek.c

hpdaemon.o:	hpdaemon.c
	cc $(CFLAGS) -D$(CMODE) -D$(CUTTER) -c -o hpdaemon.o hpdaemon.c

logerr.o:	logerr.c
	cc $(CFLAGS) -D$(CMODE) -D$(CUTTER) -c -o logerr.o logerr.c

openargs.o:	openargs.c
	cc $(CFLAGS) -D$(CMODE) -D$(CUTTER) -c -o openargs.o openargs.c

pagefeed.o:	pagefeed.c
	cc $(CFLAGS) -D$(CMODE) -D$(CUTTER) -c -o pagefeed.o pagefeed.c

plotem.o:	plotem.cc
	$(SSPP) -c -$(SSPPFLAGS) plotem.cc > plotem.c
	cc $(CFLAGS) -D$(CMODE) -D$(CUTTER) -c -o plotem.o plotem.c
	rm -f plotem.c


install:
	mv -f hpdaemon $(SP_LOCAL)/bin/hpdaemon
	chmod 755 $(SP_LOCAL)/bin/hpdaemon

install2:
	mv hpdaemon2 $(SP_LOCAL)/bin/hpdaemon2
	chmod 755 $(SP_LOCAL)/bin/hpdaemon2

finishplt.o:	hpdaemon.h
finishup.o:	hpdaemon.h
greek.o:	hpdaemon.h
hpdaemon.o:	hpdaemon.h
hpdaemon2.o:	hpdaemon.h
initplottr.o:	hpdaemon.h
initplottr2.o:	hpdaemon.h
initport.o:	hpdaemon.h
initport2.o:	hpdaemon.h
logerr.o:	hpdaemon.h
openargs.o:	hpdaemon.h
pagefeed.o:	hpdaemon.h
plotem.o:	hpdaemon.h
