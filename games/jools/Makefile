# New ports collection makefile for:	jools
# Date created:				6 June 2003
# Whom:					Adam Weinberger <adamw@FreeBSD.org>
#
# $FreeBSD$

PORTNAME=	jools
PORTVERSION=	0.20
PORTREVISION=	6
CATEGORIES=	games
MASTER_SITES=	http://pessimization.com/software/jools/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Addictive jewel-swapping puzzle game

RUN_DEPENDS=	${PYTHON_SITELIBDIR}/pygame/__init__.py:${PORTSDIR}/devel/py-game

USE_PYTHON=	yes
USE_PYDISTUTILS=	yes

post-patch:
	@${FIND} ${WRKSRC} -name ".arch-ids" | ${XARGS} ${RM} -r

.include <bsd.port.mk>
