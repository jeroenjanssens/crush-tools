BUILT_SOURCES = main.c usage.c cutfield_main.h

$(BUILT_SOURCES) : args.tab
	"$(CGENER)" -a ./args.tab

bin_PROGRAMS = cutfield
cutfield_SOURCES = cutfield.c $(BUILT_SOURCES)
cutfield_LDADD = ../libcrush/libcrush.la

CLEANFILES = $(BUILT_SOURCES)

LOG_COMPILER = $(top_srcdir)/src/bin/testharness.sh
TESTS = test.conf

EXTRA_DIST = args.tab test.conf \
             test/test_01.sh \
             test/test_02.sh \
             test/test_03.sh \
             test/test_04.sh
man1_MANS = cutfield.1
cutfield.1 : args.tab
	../bin/genman.pl args.tab > $@
