# Created by: Chris D. Faulhaber <jedgar@FreeBSD.org>
# $FreeBSD$

PORTNAME=	pngcrush
PORTVERSION=	1.7.59
CATEGORIES=	graphics
MASTER_SITES=	SF/pmt/${PORTNAME}/${PORTVERSION}/
DISTNAME=	${PORTNAME}-${PORTVERSION}-nolib

MAINTAINER=	jsa@FreeBSD.org
COMMENT=	Optimizer for PNG files

LIB_DEPENDS=	png15:${PORTSDIR}/graphics/png

USE_XZ=		yes
CFLAGS+=	-DPNGCRUSH_COUNT_COLORS -I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib
MAKE_ARGS+=	CC="${CC}" CFLAGS="${CFLAGS}" LD="${CC}" LDFLAGS="${LDFLAGS}"

PLIST_FILES=	bin/pngcrush

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/pngcrush ${PREFIX}/bin/pngcrush

.include <bsd.port.mk>
