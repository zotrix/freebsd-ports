# $FreeBSD$

PORTNAME=	plone.subrequest
PORTVERSION=	1.6.7
CATEGORIES=	www python zope
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	zope@FreeBSD.org
COMMENT=	Subrequests for Zope2

LICENSE=	GPLv2

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}five.globalrequest>=0:${PORTSDIR}/devel/py-five.globalrequest \
		${PYTHON_PKGNAMEPREFIX}zope.globalrequest>=0:${PORTSDIR}/devel/py-zope.globalrequest

DIST_SUBDIR=	zope
USE_PYTHON=	yes
USE_PYDISTUTILS=	easy_install
USE_ZIP=	yes

.include <bsd.port.mk>
