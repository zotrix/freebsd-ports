# New ports collection makefile for:	netspeed_applet
# Date created:				08 February 2003
# Whom:					Joe Marcus Clarke <marcus@FreeBSD.org>
#
# $FreeBSD$
#    $MCom: ports/net/netspeed_applet/Makefile,v 1.2 2007/05/19 21:36:17 marcus Exp $

PORTNAME=	netspeed_applet
PORTVERSION=	0.16
PORTREVISION=	1
CATEGORIES=	net gnome
MASTER_SITES=	http://launchpadlibrarian.net/49741506/

MAINTAINER=	gnome@FreeBSD.org
COMMENT=	Applet that shows how much network traffic occurs on an interface

LIB_DEPENDS=	gtop-2.0:${PORTSDIR}/devel/libgtop

INSTALLS_OMF=	yes
USE_GMAKE=	yes
USE_GNOME=	gnomehier intlhack gnomeprefix gnomehack gnomepanel
USES=		gettext
GNU_CONFIGURE=	yes
INSTALLS_ICONS=	yes
CPPFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib

.include <bsd.port.mk>
