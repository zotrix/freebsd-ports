# New ports collection makefile for:	gkrellmfmonitor
# Date Created:		08 Sep 2002
# Whom:			Jean-Yves Lefort <jylefort@brutele.be>
#
# $FreeBSD$
# $Id: Makefile,v 1.2 2002/11/09 03:14:54 jylefort Exp $
#

PORTNAME=	gkrellmfmonitor
PORTVERSION=	0.3
PORTREVISION=	8
CATEGORIES=	misc
MASTER_SITES=	# none
DISTNAME=	fmonitor-${PORTVERSION}
EXTRACT_SUFX=	.tgz

MAINTAINER=	ports@FreeBSD.org
COMMENT=	GKrellM FMonitor plugin

BUILD_DEPENDS=	${LOCALBASE}/include/gkrellm/gkrellm.h:${PORTSDIR}/sysutils/gkrellm
RUN_DEPENDS=	gkrellm:${PORTSDIR}/sysutils/gkrellm

PLIST_FILES=	libexec/gkrellm/plugins/fmonitor.so
USE_GNOME=	imlib
ALL_TARGET=	fmonitor.so
CFLAGS+=	-fPIC `${GTK_CONFIG} --cflags` `imlib-config --cflags-gdk`
MAKE_ARGS=	CC="${CC} ${CFLAGS}" GTK_LIB="`${GTK_CONFIG} --libs`"

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/fmonitor.so ${PREFIX}/libexec/gkrellm/plugins

.include <bsd.port.mk>
