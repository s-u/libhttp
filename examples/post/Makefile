# 
# Copyright (c) 2013 No Face Press, LLC
# License http://opensource.org/licenses/mit-license.php MIT License
#

#This makefile is used to test the other Makefiles


PROG = post
SRC = post.c

TOP = ../..
LIBHTTP_LIB = libhttp.a

CFLAGS = -I$(TOP)/include $(COPT)
LIBS = -lpthread

include $(TOP)/resources/Makefile.in-os

ifeq ($(TARGET_OS),LINUX) 
	LIBS += -ldl
endif

all: $(PROG)

$(PROG): $(LIBHTTP_LIB) $(SRC)
	$(CC) -o $@ $(CFLAGS) $(LDFLAGS) $(SRC) $(LIBHTTP_LIB) $(LIBS)

$(LIBHTTP_LIB):
	$(MAKE) -C $(TOP) lib && cp -p $(TOP)/lib/$(LIBHTTP_LIB) .

clean:
	rm -f $(PROG) $(LIBHTTP_LIB)

.PHONY: all clean
