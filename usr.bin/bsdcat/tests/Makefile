# $FreeBSD$

PACKAGE=	tests

_LIBARCHIVEDIR=	${SRCTOP}/contrib/libarchive

ATF_TESTS_SH+=	functional_test

BINDIR=		${TESTSDIR}

PROGS+=		bsdcat_test

CFLAGS+=	-DPLATFORM_CONFIG_H=\"${SRCTOP}/lib/libarchive/config_freebsd.h\"
CFLAGS+=	-I${SRCTOP}/lib/libarchive -I${.OBJDIR}

CFLAGS+=	-I${.OBJDIR}
CFLAGS+=	-I${_LIBARCHIVEDIR}/cat -I${_LIBARCHIVEDIR}/cat/test
CFLAGS+=	-I${_LIBARCHIVEDIR}/libarchive
CFLAGS+=	-I${_LIBARCHIVEDIR}/libarchive_fe -I${_LIBARCHIVEDIR}/test_utils

# Uncomment to link against dmalloc
#LDADD+= -L/usr/local/lib -ldmalloc
#CFLAGS+= -I/usr/local/include -DUSE_DMALLOC

.PATH:	${_LIBARCHIVEDIR}/cat/test
TESTS_SRCS=	\
	test_0.c				\
	test_empty_gz.c				\
	test_empty_lz4.c			\
	test_empty_xz.c				\
	test_error.c				\
	test_error_mixed.c			\
	test_expand_Z.c				\
	test_expand_bz2.c			\
	test_expand_gz.c			\
	test_expand_lz4.c			\
	test_expand_mixed.c			\
	test_expand_plain.c			\
	test_expand_xz.c			\
	test_help.c				\
	test_version.c

SRCS.bsdcat_test= list.h			\
	${TESTS_SRCS}

.PATH:	${_LIBARCHIVEDIR}/test_utils
SRCS.bsdcat_test+=	test_main.c		\
			test_utils.c

LIBADD.bsdcat_test=	archive

list.h: ${TESTS_SRCS} Makefile
	@(cd ${_LIBARCHIVEDIR}/tar/test && \
	grep -h DEFINE_TEST ${.ALLSRC:N*Makefile}) > ${.TARGET}.tmp
	@mv ${.TARGET}.tmp ${.TARGET}

CLEANFILES+=	list.h list.h.tmp

FILES+=	test_empty.gz.uu
FILES+=	test_empty.lz4.uu
FILES+=	test_empty.xz.uu
FILES+=	test_expand.Z.uu
FILES+=	test_expand.bz2.uu
FILES+=	test_expand.gz.uu
FILES+=	test_expand.lz4.uu
FILES+=	test_expand.plain.uu
FILES+=	test_expand.xz.uu

.include <bsd.test.mk>
