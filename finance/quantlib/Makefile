# ex:ts=8
# New ports collection makefile for:	quantlib
# Date created:			Aug 12, 2001
# Whom:				ijliao
#
# $FreeBSD$
#

PORTNAME=	quantlib
PORTVERSION=	1.1
PORTREVISION=	1
CATEGORIES=	finance
MASTER_SITES=	SF/${PORTNAME}/QuantLib/${PORTVERSION}
DISTNAME=	QuantLib-${PORTVERSION}

MAINTAINER=	dikshie@sfc.wide.ad.jp
COMMENT=	A comprehensive software framework for quantitative finance

LIB_DEPENDS=	boost_thread:${PORTSDIR}/devel/boost-libs

WRKSRC=		${WRKDIR}/QuantLib-${PORTVERSION}

USE_AUTOTOOLS=	libtool
GNU_CONFIGURE=	yes
CPPFLAGS+=	${PTHREAD_CFLAGS} -I${LOCALBASE}/include
LDFLAGS+=	${PTHREAD_LIBS} -L${LOCALBASE}/lib
USE_LDCONFIG=	yes

BROKEN=		fails to build

MAN1=		quantlib-config.1 quantlib-test-suite.1

.include <bsd.port.pre.mk>

.if ${ARCH} == "ia64" || ${ARCH} == "alpha"
BROKEN=		Does not build on ia64 or alpha
.endif

post-patch:
	@${FIND} ${WRKSRC} -name "Makefile.in" | ${XARGS} ${REINPLACE_CMD} -e \
		's|: install-dist_lispLISP|:|g ; \
		 s|@CPPUNIT_FOUND_TRUE@|#|g ; \
		 s|@CPPUNIT_FOUND_FALSE@||g'
	@${REINPLACE_CMD} -e 's|-release $$(PACKAGE_VERSION)||' ${WRKSRC}/ql/Makefile.in

post-install:
	${INSTALL_DATA} ${WRKSRC}/quantlib.el ${PREFIX}/share/emacs/site-lisp

.include <bsd.port.post.mk>
