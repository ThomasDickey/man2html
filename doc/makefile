# $Id: makefile,v 1.1 2022/07/14 00:11:48 tom Exp $

THIS		= man2html
PART		= 1

NO_LOCALE	= LANG=C LC_ALL=C LC_CTYPE=C
NR_OPTION	= -man -rHY=0 -rLL=78n -rLT=78n 
MY_OPTION	= -index -title="$(THIS)($(PART))" -compress -pgsize 99999

ALL		= $(THIS).txt $(THIS).html $(THIS).ps

all: $(ALL)

clobber:
	rm -f $(ALL)

$(THIS).txt:	$(THIS).1
	$(NO_LOCALE) nroff $(NR_OPTION) -Tascii $(THIS).1 | col -bx >$@
$(THIS).html:	$(THIS).1
	$(NO_LOCALE) nroff $(NR_OPTION) $(THIS).1 | man2html $(MY_OPTION) >$@
$(THIS).ps:	$(THIS).1
	$(NO_LOCALE) groff -man $(THIS).1 >$@
