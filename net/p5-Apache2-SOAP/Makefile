# New ports collection makefile for:	Apache2-SOAP
# Date Created:				26 January 2006
# Whom:					Simun Mikecin <numisemis@yahoo.com>
#
# $FreeBSD$
#

PORTNAME=	Apache2-SOAP
PORTVERSION=	0.73
PORTREVISION=	2
CATEGORIES=	net www perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	numisemis@yahoo.com
COMMENT=	Apache2 mod_perl2 SOAP Server

BUILD_DEPENDS=	${APACHE_PKGNAMEPREFIX}mod_perl2>=0:${PORTSDIR}/www/mod_perl2 \
		p5-SOAP-Lite>=0:${PORTSDIR}/net/p5-SOAP-Lite
RUN_DEPENDS:=	${BUILD_DEPENDS}

PERL_CONFIGURE=	yes
USE_APACHE=	22+

MAN3=		Apache2::SOAP.3

.include <bsd.port.mk>
