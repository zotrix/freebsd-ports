# Created by: Samuel Tardieu <sam@inf.enst.fr>
# $FreeBSD$

PORTNAME=	ltxml
PORTVERSION=	1.2.9
CATEGORIES=	textproc
MASTER_SITES=	GENTOO/distfiles \
		ftp://ftp.cogsci.ed.ac.uk/pub/LTXML/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	XML Toolkit

LICENSE=	GPLv2
LICENSE_FILE=	${WRKDIR}/${DISTNAME}/COPYING

OPTIONS_DEFINE=	OPTIMIZED_CFLAGS

WRKSRC=		${WRKDIR}/${DISTNAME}/XML

USES=		perl5
USE_GMAKE=	yes
GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--with-zlib=/usr --datadir=${PREFIX}/lib/ltxml12

.include <bsd.port.pre.mk>

.if ${PORT_OPTIONS:MOPTIMIZED_CFLAGS}
CFLAGS+=	-Wuninitialized -ffast-math -finline-functions -fomit-frame-pointer -fexpensive-optimizations -O3
.endif

.if ${ARCH} == "amd64" || ${ARCH} == "ia64"
CFLAGS+=	-fPIC
.endif

post-patch:
	@${REINPLACE_CMD} -e 's|CFLAGS=.*$$|CFLAGS=\$$CFLAGS|g ; \
		 s|CXXFLAGS=.*$$|CXXFLAGS=\$$CXXFLAGS|g' ${WRKSRC}/configure

.include <bsd.port.post.mk>
