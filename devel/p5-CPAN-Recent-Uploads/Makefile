# New ports collection makefile for:	p5-CPAN-Recent-Uploads
# Date created:		2011-08-26
# Whom:			Lars Thegler <lth@FreeBSD.org>
#
# $FreeBSD$
#

PORTNAME=	CPAN-Recent-Uploads
PORTVERSION=	0.06
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:BINGOS
PKGNAMEPREFIX=	p5-

MAINTAINER=	lth@FreeBSD.org
COMMENT=	Find the distributions recently uploaded to CPAN

RUN_DEPENDS=	p5-libwww>=5.835:${PORTSDIR}/www/p5-libwww \
		p5-URI>=1.56:${PORTSDIR}/net/p5-URI \
		p5-YAML-Syck>=1.15:${PORTSDIR}/textproc/p5-YAML-Syck
BUILD_DEPENDS:=	${RUN_DEPENDS}

USES=		perl5
USE_PERL5=	configure

MAN3=		CPAN::Recent::Uploads.3 \
		CPAN::Recent::Uploads::Retriever.3

.include <bsd.port.mk>
