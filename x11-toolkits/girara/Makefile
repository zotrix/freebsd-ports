# Created by: Mike Krutov <neko@takino.org>
# $FreeBSD$

PORTNAME=	girara
PORTVERSION=	0.1.7
CATEGORIES=	x11-toolkits graphics
MASTER_SITES=	http://pwmt.org/projects/girara/download/

MAINTAINER=	madpilot@FreeBSD.org
COMMENT=	GTK2 Interface Library for Zathura PDF Viewer

USE_GNOME=	glib20 gtk20
USES=		gmake
USE_LDCONFIG=	yes

.include <bsd.port.options.mk>

.if exists(/usr/bin/clang) && ${OSVERSION} > 900014
CC=		/usr/bin/clang
CPP=		/usr/bin/clang-cpp
CXX=		/usr/bin/clang++
.else
USE_GCC=	4.6+
.endif

.if ${PORT_OPTIONS:MNLS}
USES+=		gettext
PLIST_SUB+=	NLS=""
.else
PLIST_SUB+=	NLS="@comment "
.endif

LIBDIR=		${PREFIX}/lib

post-patch:	.SILENT
	${REINPLACE_CMD} -e 's|$${LIBDIR}/pkgconfig|${PREFIX}/libdata/pkgconfig|g'\
		${WRKSRC}/Makefile
.if ! ${PORT_OPTIONS:MNLS}
	${REINPLACE_CMD} -e '/-C po/d'\
		${WRKSRC}/Makefile
.endif

.include <bsd.port.mk>
