# Created by: Andrew Pantyukhin <infofarmer@FreeBSD.org>
# $FreeBSD$

PORTNAME=	gimmage
PORTVERSION=	0.2.3
PORTREVISION=	9
CATEGORIES=	graphics
MASTER_SITES=	BERLIOS CENKES

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Simple image viewer

LIB_DEPENDS=	gtkmm-2.4.1:${PORTSDIR}/x11-toolkits/gtkmm24 \
		curl:${PORTSDIR}/ftp/curl

USES=		gettext
GNU_CONFIGURE=	yes
LDFLAGS+=	-lintl

.include <bsd.port.mk>
