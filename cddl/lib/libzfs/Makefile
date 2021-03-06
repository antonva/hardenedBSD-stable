# $FreeBSD$

.PATH: ${SRCTOP}/cddl/compat/opensolaris/misc
.PATH: ${SRCTOP}/sys/cddl/contrib/opensolaris/common/zfs
.PATH: ${SRCTOP}/sys/cddl/contrib/opensolaris/uts/common/fs/zfs
.PATH: ${SRCTOP}/cddl/contrib/opensolaris/lib/libzfs/common

LIB=	zfs
DPADD=	${LIBMD} ${LIBPTHREAD} ${LIBUMEM} ${LIBUTIL} ${LIBM} ${LIBNVPAIR} \
	${LIBAVL} ${LIBZFS_CORE} ${LIBUUTIL} ${LIBBSDXML} ${LIBGEOM} \
	${LIBNVPAIR} ${LIBZ}

LDADD=	-lmd -lpthread -lumem -lutil -luutil -lm -lnvpair -lavl \
	-lbsdxml -lgeom -lnvpair -lz -lzfs_core

SRCS=	deviceid.c \
	fsshare.c \
	mkdirp.c \
	mnttab.c \
	thread_pool.c \
	zmount.c \
	zone.c

SRCS+=	libzfs_changelist.c \
	libzfs_compat.c \
	libzfs_config.c \
	libzfs_dataset.c \
	libzfs_diff.c \
	libzfs_import.c \
	libzfs_iter.c \
	libzfs_mount.c \
	libzfs_pool.c \
	libzfs_sendrecv.c \
	libzfs_status.c \
	libzfs_util.c \
	zfeature_common.c \
	zfs_comutil.c \
	zfs_deleg.c \
	zfs_fletcher.c \
	zfs_namecheck.c \
	zfs_prop.c \
	zpool_prop.c \
	zprop_common.c \

WARNS?=	0
CSTD=	c99
CFLAGS+= -DZFS_NO_ACL
CFLAGS+= -I${SRCTOP}/sbin/mount
CFLAGS+= -I${SRCTOP}/sys/cddl/compat/opensolaris
CFLAGS+= -I${SRCTOP}/cddl/compat/opensolaris/include
CFLAGS+= -I${SRCTOP}/cddl/compat/opensolaris/lib/libumem
CFLAGS+= -I${SRCTOP}/cddl/contrib/opensolaris/lib/libzpool/common
CFLAGS+= -I${SRCTOP}/sys/cddl/contrib/opensolaris/common/zfs
CFLAGS+= -I${SRCTOP}/sys/cddl/contrib/opensolaris/uts/common/fs/zfs
CFLAGS+= -I${SRCTOP}/sys/cddl/contrib/opensolaris/uts/common/sys
CFLAGS+= -I${SRCTOP}/cddl/contrib/opensolaris/head
CFLAGS+= -I${SRCTOP}/sys/cddl/contrib/opensolaris/uts/common
CFLAGS+= -I${SRCTOP}/cddl/contrib/opensolaris/lib/libnvpair
CFLAGS+= -I${SRCTOP}/cddl/contrib/opensolaris/lib/libuutil/common
CFLAGS+= -I${SRCTOP}/cddl/contrib/opensolaris/lib/libzfs/common
CFLAGS+= -I${SRCTOP}/cddl/contrib/opensolaris/lib/libzfs_core/common

.include <bsd.lib.mk>
