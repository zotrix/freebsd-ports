# New ports collection makefile for:	ExtUtils::ParseXS
# Date created:				29 June 2003
# Whom:                			Dmitry Sivachenko <demon@FreeBSD.org>
#
# $FreeBSD$
#

PORTNAME=	ExtUtils-ParseXS
PORTVERSION=	3.18
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:SMUELLER
PKGNAMEPREFIX=	p5-

MAINTAINER=	demon@FreeBSD.org
COMMENT=	Converts Perl XS code into C code

PERL_CONFIGURE=	yes

MAN3=		ExtUtils::ParseXS.3 \
		ExtUtils::ParseXS::Constants.3 \
		ExtUtils::ParseXS::Utilities.3 \
		ExtUtils::Typemaps.3 \
		ExtUtils::Typemaps::Cmd.3 \
		ExtUtils::Typemaps::InputMap.3 \
		ExtUtils::Typemaps::OutputMap.3 \
		ExtUtils::Typemaps::Type.3

.include <bsd.port.pre.mk>

post-patch:
	@${REINPLACE_CMD} -e '/EXE_FILES/d' ${WRKSRC}/Makefile.PL

.include <bsd.port.post.mk>
