# Created by: Aaron Dalton <aaron@FreeBSD.org>
# $FreeBSD$

PORTNAME=	CGI-Untaint-date
PORTVERSION=	1.00
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Validate a date

BUILD_DEPENDS=	p5-CGI-Untaint>=0:${PORTSDIR}/www/p5-CGI-Untaint \
		p5-Date-Manip>=0:${PORTSDIR}/devel/p5-Date-Manip \
		p5-Date-Simple>=0:${PORTSDIR}/devel/p5-Date-Simple
RUN_DEPENDS:=	${BUILD_DEPENDS}

MAN3=	CGI::Untaint::date.3

USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
