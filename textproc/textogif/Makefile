# New ports collection makefile for:	textogif
# Date created:		2006-02-04
# Whom:			Nicola Vitale	<nivit@email.it>
#
# $FreeBSD$
#

PORTNAME=	textogif
PORTVERSION=	1.1
PORTREVISION=	4
CATEGORIES=	textproc math www
MASTER_SITES=	http://www.fourmilab.ch/webtools/textogif/download/ \
		http://nivi.interfree.it/distfiles/${PORTNAME}/
DISTNAME=	${PORTNAME}_${PORTVERSION}

MAINTAINER=	nivit@FreeBSD.org
COMMENT=	A Perl script to convert LaTeX formulas into GIFs

RUN_DEPENDS=	ppmtogif:${PORTSDIR}/graphics/netpbm

NO_BUILD=	yes
USE_TEX=	latex dvipsk
USE_PERL5_RUN=	yes

do-install:
	@cd ${WRKDIR};\
	${INSTALL_SCRIPT} ${PORTNAME} ${PREFIX}/bin

.include <bsd.port.mk>
