# Created by: Alexandros Kosiaris <akosiaris+ports@gmail.com>
# $FreeBSD$

PORTNAME=	jira
PORTVERSION=	0.13
CATEGORIES=	devel python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	jira-python-${DISTVERSIONPREFIX}${DISTVERSION}${DISTVERSIONSUFFIX}

MAINTAINER=	akosiaris+ports@gmail.com
COMMENT=	Library to ease use of the JIRA 5 REST APIs

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}requests>=1.0.0:${PORTSDIR}/www/py-requests \
		${PYTHON_PKGNAMEPREFIX}requests-oauthlib>=0.3.0:${PORTSDIR}/www/py-requests-oauthlib \
		ipython${PYTHON_PKGNAMESUFFIX}>=0:${PORTSDIR}/devel/ipython \
		${PYTHON_PKGNAMEPREFIX}tlslite>=0.4.1:${PORTSDIR}/security/py-tlslite \
		${PYTHON_PKGNAMEPREFIX}pycrypto>=0:${PORTSDIR}/security/py-pycrypto

USE_PYTHON=		yes
USE_PYDISTUTILS=	easy_install
PYDISTUTILS_PKGNAME=	jira_python

.include <bsd.port.mk>
