# Created by: Cezary Morga <cm@therek.net>
# $FreeBSD$

PORTNAME=	Olson-Abbreviations
PORTVERSION=	0.04
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:ECARROLL
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Globally unique timezones abbreviation handling

RUN_DEPENDS=	p5-Moose>=0.41:${PORTSDIR}/devel/p5-Moose \
		p5-MooseX-AttributeHelpers>=0:${PORTSDIR}/devel/p5-MooseX-AttributeHelpers \
		p5-MooseX-ClassAttribute>=0:${PORTSDIR}/devel/p5-MooseX-ClassAttribute
BUILD_DEPENDS:=	${RUN_DEPENDS}

USES=		perl5
USE_PERL5=	configure

MAN3=	Olson::Abbreviations.3

.include <bsd.port.mk>
