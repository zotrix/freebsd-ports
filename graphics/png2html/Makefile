# New ports collection makefile for:	png2html
# Date created:				11 November 1999
# Whom:					Chris D. Faulhaber <jedgar@fxp.org>
#
# $FreeBSD$
#

PORTNAME=	png2html
PORTVERSION=	1.1
PORTREVISION=	9
CATEGORIES=	graphics
MASTER_SITES=	http://www.geoffholden.com/content/projects/png2html/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Takes a PNG image and transforms it into HTML

LICENSE=	GPLv2 # (or later)
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	png15:${PORTSDIR}/graphics/png \
		gd:${PORTSDIR}/graphics/gd

PLIST_FILES=	bin/png2html

post-patch:
	@${REINPLACE_CMD} 's|CHANGE_ME|${LOCALBASE}|g' ${WRKSRC}/Makefile

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/png2html ${PREFIX}/bin

.include <bsd.port.mk>
