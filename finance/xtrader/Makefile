# New ports collection makefile for:	xtrader
# Date created:		2005-04-16
# Whom:			Michael Johnson <ahze@FreeBSD.org>
#
# $FreeBSD$
#

PORTNAME=	xtrader
PORTVERSION=	0.99.9
PORTREVISION=	8
CATEGORIES=	finance
MASTER_SITES=	SF/${PORTNAME}/OldFiles

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Technical analysis program for financial instruments

LIB_DEPENDS=	ptypes.21:${PORTSDIR}/devel/ptypes \
		fltk.1:${PORTSDIR}/x11-toolkits/fltk

MAKE_ENV=	PTHREAD_LIBS="${PTHREAD_LIBS}"
MAKEFILE=	Makefile.linux
USE_XORG=	x11 xpm
BUILD_WRKSRC=	${WRKSRC}/${PORTNAME}
NO_WRKSUBDIR=	yes
USE_GMAKE=	yes

PLIST_FILES=	bin/xtrader \
		%%DATADIR%%/sample.xt
PLIST_DIRS=	%%DATADIR%%

post-patch:
	${REINPLACE_CMD} -e 's|char|const char|' \
	    ${WRKSRC}/xtrader/src/Resource.cpp
	${REINPLACE_CMD} -e 's|static char|static const char|' \
	    ${WRKSRC}/xtrader/src/Resource.h
	${REINPLACE_CMD} -e 's|int(data)|(unsigned long)data|' \
	    ${WRKSRC}/xtrader/src/gui/XTrader.h
	${FIND} ${WRKSRC} -type f -name "*.cpp" -o -name "*.h" | ${XARGS} \
	   ${REINPLACE_CMD} -e '/^#include <FL/s|.h>$$|.H>|; s|fl_file_chooser|Fl_File_Chooser|g'

do-install:
	@${MKDIR} ${DATADIR}
	${INSTALL_DATA} ${WRKSRC}/${PORTNAME}/sample.xt ${DATADIR}
	${INSTALL_PROGRAM} ${WRKSRC}/${PORTNAME}/xtrader ${PREFIX}/bin

.include <bsd.port.mk>
