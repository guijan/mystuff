# $OpenBSD: Makefile.template,v 1.90 2021/02/25 21:59:27 sthen Exp $
COMMENT		= dictionary-based password generator
V		= 1.2.0
DISTNAME	= dictpw-${V}
CATEGORIES	= security
HOMEPAGE	= https://github.com/guijan/dictpw

# I'm the author and an OpenBSD user, you can also open a PR/issue at $HOMEPAGE
MAINTAINER	= Guilherme Janczak <guilherme.janczak@yandex.com>

# ISC
PERMIT_PACKAGE	= Yes

# uses pledge()
WANTLIB		= c

MASTER_SITES	= https://github.com/guijan/dictpw/releases/download/v${V}/
EXTRACT_SUFX	= .tar.xz

COMPILER	= base-clang ports-gcc base-gcc
COMPILER_LANGS	= c

MODULES		= devel/meson

# disable meson's default of using "-Wl,--as-needed" on ld.bfd arches;
# build failures due to undefined references are often seen.
.include <bsd.port.arch.mk>
.if !${PROPERTIES:Mlld}
CONFIGURE_ARGS	+=       -Db_asneeded=false
.endif

.include <bsd.port.mk>
