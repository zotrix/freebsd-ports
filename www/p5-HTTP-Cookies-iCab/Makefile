# Created by: Gea-Suan Lin <gslin@gslin.org>
# $FreeBSD$

PORTNAME=	HTTP-Cookies-iCab
PORTVERSION=	1.131
PORTREVISION=	1
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Cookie storage and management for iCab

LICENSE=	ART10 GPLv1
LICENSE_COMB=	dual

BUILD_DEPENDS=	p5-HTTP-Cookies>=0:${PORTSDIR}/www/p5-HTTP-Cookies
RUN_DEPENDS=	p5-HTTP-Cookies>=0:${PORTSDIR}/www/p5-HTTP-Cookies
TEST_DEPENDS=	p5-Text-Diff>=0:${PORTSDIR}/textproc/p5-Text-Diff

USES=		perl5
USE_PERL5=	configure

MAN3=		HTTP::Cookies::iCab.3

.include <bsd.port.mk>
