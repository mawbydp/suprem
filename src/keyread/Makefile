# Makefile for the SupremIV formatted key file reader.
#
# Makefile 3.1 9/14/87 10:43:51
# modified: Mon Feb  1 11:36:39 PST 1993, Stephen E. Hansen
#

SYS     = BSD
LOCDEFS = -D$(SYS)
INCLUDE = -I../include
CFLAGS  = -c $(COPT) $(LOCDEFS) $(INCLUDE)

HFILES  =
SCCS	= s.expand.c s.lexical.l s.main.c s.parser.y s.write.c
SRCS	= expand.c lexical.l main.c parser.y write.c
CSRCS	= expand.c lexical.c main.c parser.c write.c
OBJS	= expand.o main.o parser.o write.o
LIBS	= -lm
SLIB	= ../misc/bsd.o

keyread : $(OBJS)
	$(CC) $(LDFLAGS) $(OBJS) $(LIBS) $(SLIB) -o $@

tags    : $(SRCS)
	ctags $(SRCS)

lint    : $(CSRCS)
	lint $(CFLAGS) $(CSRCS)

clean   :
	rm -f $(OBJS)

version :
	prs -d":Dt: :F:\n:C:\n\n" $(SCCS)

# change the default actions
.c~.o   :
	$(GET) $(GFLAGS) $<
	$(CC) $(CFLAGS) $*.c -o $*.o

.c.o   :
	$(CC) $(CFLAGS) $*.c -o $*.o

.c~.c	:
	$(GET) $(GFLAGS) $<

.y.o    :
	$(YACC) $(YFLAGS) -d $<
	mv y.tab.c $*.c
	mv y.tab.h $*.h
	$(CC) $(CFLAGS) $*.c -o $*.o

.y.c    :
	$(YACC) $(YFLAGS) -d $<
	mv y.tab.c $*.c
	mv y.tab.h $*.h

.y~.y	:
	$(GET) $(GFLAGS) $<

.l~.l	:
	$(GET) $(GFLAGS) $<

.h~.h	:
	$(GET) $(GFLAGS) $<

depend  : $(YSRCS) always
	cat Makefile.proto > Makefile
	$(CC) -M $(CFLAGS) $(SRCS) >>Makefile

always:

#----------------------------------------
# DO NOT DELETE THIS LINE -- make depend may depend on it.
expand.o: expand.c
expand.o: /usr/include/stdio.h
expand.o: ../include/check.h
expand.o: ../include/key.h
main.o: main.c
main.o: /usr/include/stdio.h
main.o: ../include/sysdep.h
#main.o: /usr/include/sys/file.h
#main.o: /usr/include/sys/types.h
#main.o: /usr/include/sys/stdtypes.h
#main.o: /usr/include/sys/sysmacros.h
#main.o: /usr/include/sys/fcntlcom.h
#main.o: /usr/include/sys/fcntl.h
#main.o: /usr/include/sys/stdtypes.h
#main.o: /usr/include/sys/stat.h
#main.o: /usr/include/sys/types.h
main.o: ../include/check.h
main.o: ../include/key.h
write.o: write.c
write.o: /usr/include/stdio.h
write.o: /usr/include/ctype.h
write.o: ../include/check.h
write.o: ../include/key.h
