# Created by: Sergey Skvortsov <skv@protey.ru>
# $FreeBSD$

PORTNAME=	hyperic-sigar
PORTVERSION=	1.6.4
CATEGORIES=	sysutils
MASTER_SITES=	SF
MASTER_SITE_SUBDIR=	sigar/sigar/${PORTVERSION:C/\.[0-9]+$//}
DISTNAME=	${PORTNAME}-${PORTVERSION}-src

MAINTAINER=	ports@FreeBSD.org
COMMENT=	SIGAR - System Information Gatherer and Reporter

WRKSRC=		${WRKDIR}/${DISTNAME}/bindings/java/

USES=		perl5
USE_JAVA=	yes
JAVA_VERSION=	1.6+
USE_ANT=	yes
USE_PERL5=	build
USE_LDCONFIG=	yes

SHLIB_MAJOR=	0
PLIST_SUB=	SHLIB_MAJOR="${SHLIB_MAJOR}"

.include <bsd.port.pre.mk>
.if ${OSVERSION} > 900007
BROKEN=	fails to build with new utmpx
.endif

do-install:
	${MKDIR} ${PREFIX}/include ${PREFIX}/lib ${JAVAJARDIR}
	${INSTALL_DATA} ${WRKSRC}/sigar-bin/include/*.h ${PREFIX}/include/
	${INSTALL_DATA} ${WRKSRC}/sigar-bin/lib/libsigar-*.so ${PREFIX}/lib/libsigar.so.${SHLIB_MAJOR}
	${LN} -sf ${PREFIX}/lib/libsigar.so.${SHLIB_MAJOR} ${PREFIX}/lib/libsigar.so
	${INSTALL_DATA} ${WRKSRC}/sigar-bin/lib/sigar.jar ${JAVAJARDIR}/

.include <bsd.port.post.mk>
