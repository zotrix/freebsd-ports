# New ports collection makefile for:  igmpproxy
# Date created:	       5 January 2009
# Whom:		       asami
#
# $FreeBSD$
#

PORTNAME=	igmpproxy
PORTVERSION=	0.1
PORTREVISION=	1
PORTEPOCH=	1
CATEGORIES=	net
MASTER_SITES=	${MASTER_SITE_SOURCEFORGE}
MASTER_SITE_SUBDIR=	${PORTNAME}/${PORTNAME}/${PORTVERSION}

MAINTAINER=	melifaro@ipfw.ru
COMMENT=	Multicast forwarding IGMP proxy

HOMEPAGE=	http://igmpproxy.sourceforge.net/

USE_RC_SUBR=	igmpproxy
USE_GMAKE=	yes
GNU_CONFIGURE=	yes

MAN5=		igmpproxy.conf.5
MAN8=		igmpproxy.8

.include <bsd.port.mk>
