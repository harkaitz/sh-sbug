.POSIX:
.SUFFIXES:
.PHONY: all clean install check

PROJECT   =sbug
VERSION   =1.0.0
PREFIX    =/usr/local
BUILDDIR ?=.build
EXE      ?=$(shell uname -s | awk '/Windows/ || /MSYS/ || /CYG/ { print ".exe" }')

all:
clean:
install:
check:
## -- BLOCK:license --
install: install-license
install-license: README.md COPYING
	mkdir -p $(DESTDIR)$(PREFIX)/share/doc/$(PROJECT)
	cp README.md COPYING $(DESTDIR)$(PREFIX)/share/doc/$(PROJECT)
## -- BLOCK:license --
## -- BLOCK:sh --
install: install-sh
install-sh:
	mkdir -p $(DESTDIR)$(PREFIX)/bin
	cp bin/sbug $(DESTDIR)$(PREFIX)/bin
	cp bin/sbug-ctl $(DESTDIR)$(PREFIX)/bin
## -- BLOCK:sh --
