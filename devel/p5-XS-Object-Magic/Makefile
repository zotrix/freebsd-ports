# New ports collection makefile for:	p5-XS-Object-Magic
# Date created:		2011-11-05
# Whom:			Sunpoet Po-Chuan Hsieh <sunpoet@FreeBSD.org>
#
# $FreeBSD$
#

PORTNAME=	XS-Object-Magic
PORTVERSION=	0.04
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:FLORA
PKGNAMEPREFIX=	p5-

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Opaque, extensible XS pointer backed objects using sv_magic

BUILD_DEPENDS=	p5-ExtUtils-Depends>=0.302:${PORTSDIR}/devel/p5-ExtUtils-Depends

TEST_DEPENDS=	p5-Test-Fatal>=0:${PORTSDIR}/devel/p5-Test-Fatal \
		p5-Test-use-ok>=0:${PORTSDIR}/devel/p5-Test-use-ok

PERL_CONFIGURE=	yes

MAN3=		XS::Object::Magic.3

.include <bsd.port.mk>
