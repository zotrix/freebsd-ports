# Created by: swills@
# $FreeBSD$

PORTNAME=	Net-LDAP-Server-Test
PORTVERSION=	0.19
CATEGORIES=	net perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Perl module to test Net::LDAP code

LICENSE=	ART10 GPLv1
LICENSE_COMB=	dual

BUILD_DEPENDS=	p5-Data-Dump>=0:${PORTSDIR}/devel/p5-Data-Dump \
		p5-Net-LDAP-Server>=0.3:${PORTSDIR}/net/p5-Net-LDAP-Server \
		p5-perl-ldap>=0:${PORTSDIR}/net/p5-perl-ldap

USES=		perl5
USE_PERL5=	configure

MAN3=		Net::LDAP::Server::Test.3

.include <bsd.port.mk>
