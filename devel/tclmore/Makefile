# New ports collection makefile for:	tclmore
# Date created:				Tue Apr 25 16:20:49 MSD 2006
# Whom:					Denis Shaposhnikov <dsh@vlink.ru>
#
# $FreeBSD$
#

PORTNAME=	tclmore
PORTVERSION=	0.7b1
PORTREVISION=	1
CATEGORIES=	devel tcl
MASTER_SITES=	http://download.gna.org/tclmore/0.7/
DISTNAME=	${PORTNAME}_${PORTVERSION}_src

MAINTAINER=	dsh@vlink.ru
COMMENT=	More TCL commands

GNU_CONFIGURE=	yes
USE_GMAKE=	yes
USE_LDCONFIG=	yes
USE_TCL=	yes
WRKSRC=		${WRKDIR}/${DISTNAME:S/_src$//}

INFO=		${PORTNAME}

CONFIGURE_ARGS+=--with-tcl=${TCL_LIBDIR} \
		--enable-threads

.include <bsd.port.mk>
