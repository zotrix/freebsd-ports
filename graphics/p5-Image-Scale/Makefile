# Created by: Mark Atkinson <atkin901@gmail.com>
# $FreeBSD$

PORTNAME=	Image-Scale
PORTVERSION=	0.08
PORTREVISION=	2
CATEGORIES=	graphics perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	atkin901@gmail.com
COMMENT=	Perl module for fast, high-quality fixed-point image resizing

LICENSE=	GPLv2

LIB_DEPENDS=	jpeg:${PORTSDIR}/graphics/jpeg \
		png15:${PORTSDIR}/graphics/png \
		gif:${PORTSDIR}/graphics/giflib
TEST_DEPENDS=	p5-Test-NoWarnings>=0:${PORTSDIR}/devel/p5-Test-NoWarnings

MAN3=		Image::Scale.3

PERL_CONFIGURE=	yes

.include <bsd.port.mk>
