#  Make WWW under unix for a.n.other unix system (bsd)
#   Use this as a template

# For W3 distribution, machine type for subdirectories
WWW_MACH = djgpp

# The ASIS repository's name for the machine we are on
#ASIS_MACH = hardware/os

CFLAGS = -O3 -DUSE_ZLIB -DDOSPATH -DNOUSERS -DDEBUG \
-I../implemen \
-I../../../djgpp/tcplib/include \
-I../../../djgpp/tcplib/include/tcp \
-I../../../src \
-I../../..
LFLAGS =
CC = gcc

# Directory for installed binary:
!BINDIR = /usr/local/bin

# Where is the W3 object library to be installed (not normally done)?
LIBDIR = $(WWW)/Library/Implementation/$(WWW_MACH)

#_________________ OK if normal W3 distribution
# Where is the WWW source root?
WWW = ../..

#  Where should temporary (object) files go?
WTMP = ../..

include $(WWW)/Library/Implementation/Version.make
#include $(WWW)/Library/Implementation/CommonMakefile
include ./CommonMakefile
