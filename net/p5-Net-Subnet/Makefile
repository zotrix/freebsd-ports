# Created by: Henk van Oers <hvo.pm@xs4all.nl>
# $FreeBSD$

PORTNAME=	Net-Subnet
PORTVERSION=	1.03
CATEGORIES=	net perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Fast IP-in-subnet matcher for IPv4 and IPv6, CIDR or mask

LICENSE=	ART10

BUILD_DEPENDS=	p5-Socket6>=0.23:${PORTSDIR}/net/p5-Socket6
RUN_DEPENDS=	p5-Socket6>=0.23:${PORTSDIR}/net/p5-Socket6

USES=		perl5
USE_PERL5=	configure

MAN3=		Net::Subnet.3

.include <bsd.port.mk>
