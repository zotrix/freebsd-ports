# Created by: Frederic Culot <culot@FreeBSD.org>
# $FreeBSD$

PORTNAME=	Net-HTTP
PORTVERSION=	6.06
CATEGORIES=	net perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Low-level HTTP client

LICENSE=	ART10 GPLv1
LICENSE_COMB=	dual

BUILD_DEPENDS=	p5-IO-Socket-SSL>=1.38:${PORTSDIR}/security/p5-IO-Socket-SSL
RUN_DEPENDS=	p5-IO-Socket-SSL>=1.38:${PORTSDIR}/security/p5-IO-Socket-SSL

CONFLICTS=	p5-libwww-5*

USES=		perl5
USE_PERL5=	configure

MAN3=		Net::HTTP.3 \
		Net::HTTPS.3 \
		Net::HTTP::NB.3

.include <bsd.port.mk>
