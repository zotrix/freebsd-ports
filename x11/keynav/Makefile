# $FreeBSD$

PORTNAME=	keynav
DISTVERSION=	0.20110708.0
PORTREVISION=	1
PORTEPOCH=	1
CATEGORIES=	x11
MASTER_SITES=	http://semicomplete.googlecode.com/files/

MAINTAINER=	wxs@FreeBSD.org
COMMENT=	Quickly select a portion of the screen using minimal keystrokes

LIB_DEPENDS=	xdo.2:${PORTSDIR}/x11/xdotool \
		cairo.2:${PORTSDIR}/graphics/cairo

USE_GNOME=	glib20
USE_XORG=	xtst x11 xinerama
USE_GMAKE=	yes

PLIST_FILES=	bin/keynav
PORTEXAMPLES=	keynavrc

.include <bsd.port.pre.mk>

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/keynav ${PREFIX}/bin
.if !defined(NOPORTEXAMPLES)
	@${MKDIR} ${EXAMPLESDIR}
	${INSTALL_DATA} ${WRKSRC}/keynavrc ${EXAMPLESDIR}
.endif

.include <bsd.port.post.mk>
