# Created by: Anton Berezin <tobez@FreeBSD.org>
# $FreeBSD$

PORTNAME=	HTTP-Server-Simple-Recorder
PORTVERSION=	0.03
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	tobez@FreeBSD.org
COMMENT=	Mixin to record HTTP::Server::Simple's sockets

BUILD_DEPENDS=	p5-HTTP-Server-Simple>=0:${PORTSDIR}/www/p5-HTTP-Server-Simple \
		p5-Test-HTTP-Server-Simple>=0:${PORTSDIR}/www/p5-Test-HTTP-Server-Simple \
		p5-IO-Tee>=0:${PORTSDIR}/devel/p5-IO-Tee
RUN_DEPENDS:=	${BUILD_DEPENDS}

USES=		perl5
USE_PERL5=	configure

MAN3=	HTTP::Server::Simple::Recorder.3

.include <bsd.port.mk>
