# ex:ts=8
# Ports collection makefile for:	Finance::TW::EmergingQuote
# Created by: ijliao
# $FreeBSD$

PORTNAME=	Finance-TW-EmergingQuote
PORTVERSION=	0.26
CATEGORIES=	finance perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Check stock quotes from Taiwan Emerging Stock

BUILD_DEPENDS=	p5-libwww>=0:${PORTSDIR}/www/p5-libwww
RUN_DEPENDS:=	${BUILD_DEPENDS}

USES=		perl5
USE_PERL5=	configure

MAN3=	Finance::TW::EmergingQuote.3

.include <bsd.port.mk>
