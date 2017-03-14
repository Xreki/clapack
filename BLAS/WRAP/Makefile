TOPDIR=../..
include $(TOPDIR)/make.inc

#######################################################################
#  This is the makefile to create a wrapper for the CBLAS.
#######################################################################

.PHONY: all

all: cblaswr fblaswr

.PHONY: cblaswr

cblaswr: $(TOPDIR)/$(CBLASWRLIB)

$(TOPDIR)/$(CBLASWRLIB): cblaswr.o
	$(ARCH) $(ARCHFLAGS) $@ cblaswr.o
	$(RANLIB) $@
	
.PHONY: fblaswr

fblaswr: $(TOPDIR)/$(FBLASWRLIB)

$(TOPDIR)/$(FBLASWRLIB): fblaswr.o
	$(ARCH) $(ARCHFLAGS) $@ fblaswr.o
	$(RANLIB) $@

clean:
	rm -f *.o *.a

.c.o: 
	$(CC) $(CFLAGS) -c $*.c

