# Created by: Rod Taylor <ports@rbt.ca>
# $FreeBSD$

PORTNAME=	Text-WordDiff
PORTVERSION=	0.08
CATEGORIES=	textproc perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Track changes between documents

LICENSE=	ART10 GPLv1
LICENSE_COMB=	dual

BUILD_DEPENDS=	p5-Algorithm-Diff>=0:${PORTSDIR}/devel/p5-Algorithm-Diff \
		p5-HTML-Parser>=0:${PORTSDIR}/www/p5-HTML-Parser
RUN_DEPENDS=	p5-Algorithm-Diff>=0:${PORTSDIR}/devel/p5-Algorithm-Diff \
		p5-HTML-Parser>=0:${PORTSDIR}/www/p5-HTML-Parser

USES=		perl5
USE_PERL5=	modbuild

MAN3=		Text::WordDiff.3 \
		Text::WordDiff::ANSIColor.3 \
		Text::WordDiff::HTML.3 \
		Text::WordDiff::HTMLTwoLines.3

.include <bsd.port.mk>
