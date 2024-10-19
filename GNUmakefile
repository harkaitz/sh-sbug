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
## -- BLOCK:mkdocs --
MKDOCS=$(shell which mkdocs 2>/dev/null || true)
ifneq ($(MKDOCS),)
install: install-doc
clean: clean-doc
all: all-doc
install-doc: all-doc
	mkdir -p $(DESTDIR)$(PREFIX)/share/doc/$(PROJECT)
	cp -r site/* $(DESTDIR)$(PREFIX)/share/doc/$(PROJECT)
all-doc: site/index.html
site/index.html: README.md mkdocs.yml $(shell find docs -type f)
	cp README.md docs/index.md
	$(MKDOCS) build
clean-doc:
	rm -rf site
endif
## -- BLOCK:mkdocs --
## -- BLOCK:sh --
install: install-sh
install-sh:
	mkdir -p $(DESTDIR)$(PREFIX)/bin
	cp bin/sbug $(DESTDIR)$(PREFIX)/bin
	cp bin/chlog2html $(DESTDIR)$(PREFIX)/bin
	cp bin/sbug-ctl $(DESTDIR)$(PREFIX)/bin
	cp bin/sbug-changelog $(DESTDIR)$(PREFIX)/bin
## -- BLOCK:sh --
