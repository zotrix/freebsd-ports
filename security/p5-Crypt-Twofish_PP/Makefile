# New ports collection makefile for:  p5-Crypt-Twofish_PP
# Date created:                19 January 2010
# Whom:                        Konstantin Menshikov <kostjnspb@yandex.ru>
#
# $FreeBSD$
#

PORTNAME=	Crypt-Twofish_PP
PORTVERSION=	0.17
PORTREVISION=	1
CATEGORIES=	security perl5
MASTER_SITES=	CPAN \
		http://kostjn.spb.ru/freebsd/
PKGNAMEPREFIX=	p5-

MAINTAINER=	kostjnspb@yandex.ru
COMMENT=	The Twofish Algorithm in Pure Perl

BUILD_DEPENDS=	p5-Locale-libintl>=0:${PORTSDIR}/devel/p5-Locale-libintl
RUN_DEPENDS:=	${BUILD_DEPENDS}

PERL_CONFIGURE=	YES

MAN3=	Crypt::Twofish_PP.3 \
	Crypt::Twofish_PP::Key16.3 \
	Crypt::Twofish_PP::Key24.3 \
	Crypt::Twofish_PP::Key32.3

.include <bsd.port.mk>
