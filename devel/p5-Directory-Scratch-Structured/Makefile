# New ports collection makefile for:	devel/p5-Directory-Scratch-Structured
# Date created:				22 April 2008
# Whom:					Lars Thegler <lth@FreeBSD.org>
#
# $FreeBSD$
#

PORTNAME=	Directory-Scratch-Structured
PORTVERSION=	0.04
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	lth@FreeBSD.org
COMMENT=	Creates temporary files and directories from a structured description

USES=		perl5
USE_PERL5=	modbuild

RUN_DEPENDS=	p5-Readonly>=0:${PORTSDIR}/devel/p5-Readonly \
		p5-Sub-Exporter>=0:${PORTSDIR}/devel/p5-Sub-Exporter \
		p5-Sub-Install>=0:${PORTSDIR}/devel/p5-Sub-Install \
		p5-Data-TreeDumper>=0:${PORTSDIR}/devel/p5-Data-TreeDumper \
		p5-Directory-Scratch>=0:${PORTSDIR}/devel/p5-Directory-Scratch
BUILD_DEPENDS:=	${RUN_DEPENDS}
TEST_DEPENDS=	p5-Test-Block>0:${PORTSDIR}/devel/p5-Test-Block \
		p5-Test-Exception>0:${PORTSDIR}/devel/p5-Test-Exception \
		p5-Test-NoWarnings>0:${PORTSDIR}/devel/p5-Test-NoWarnings \
		p5-Test-Strict>0:${PORTSDIR}/devel/p5-Test-Strict \
		p5-Test-Warn>0:${PORTSDIR}/devel/p5-Test-Warn

MAN3=	Directory::Scratch::Structured.3

.include <bsd.port.mk>
