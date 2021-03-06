# Created by: James FitzGibbon <jfitz@FreeBSD.org>
# $FreeBSD$

PORTNAME=	WWW-Search
PORTVERSION=	2.509
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Perl5 module for WWW searches

BUILD_DEPENDS=	p5-Bit-Vector>=0:${PORTSDIR}/math/p5-Bit-Vector \
		p5-Date-Manip>=0:${PORTSDIR}/devel/p5-Date-Manip \
		p5-File-Slurp>=0:${PORTSDIR}/devel/p5-File-Slurp \
		p5-HTML-Parser>=2.23:${PORTSDIR}/www/p5-HTML-Parser \
		p5-HTML-Tree>=0:${PORTSDIR}/www/p5-HTML-Tree \
		p5-URI>=0:${PORTSDIR}/net/p5-URI \
		p5-User>=0:${PORTSDIR}/sysutils/p5-User \
		p5-libwww>=2:${PORTSDIR}/www/p5-libwww \
		p5-IO-Capture>=0:${PORTSDIR}/devel/p5-IO-Capture \
		p5-Pod-Coverage>=0:${PORTSDIR}/devel/p5-Pod-Coverage \
		p5-Test-File>=0:${PORTSDIR}/devel/p5-Test-File \
		p5-Test-Pod>=0:${PORTSDIR}/devel/p5-Test-Pod
RUN_DEPENDS=	p5-Bit-Vector>=0:${PORTSDIR}/math/p5-Bit-Vector \
		p5-Date-Manip>=0:${PORTSDIR}/devel/p5-Date-Manip \
		p5-File-Slurp>=0:${PORTSDIR}/devel/p5-File-Slurp \
		p5-HTML-Parser>=2.23:${PORTSDIR}/www/p5-HTML-Parser \
		p5-HTML-Tree>=0:${PORTSDIR}/www/p5-HTML-Tree \
		p5-URI>=0:${PORTSDIR}/net/p5-URI \
		p5-User>=0:${PORTSDIR}/sysutils/p5-User \
		p5-libwww>=2:${PORTSDIR}/www/p5-libwww \
		p5-Test-Pod-Coverage>=0:${PORTSDIR}/devel/p5-Test-Pod-Coverage

USES=		perl5
USE_PERL5=	configure
USE_DOS2UNIX=	yes

MAN1=		AutoSearch.1 \
		WebSearch.1
MAN3=		WWW::Search.3 \
		WWW::SearchResult.3 \
		WWW::Search::Null.3 \
		WWW::Search::Null::Count.3 \
		WWW::Search::Null::Empty.3 \
		WWW::Search::Null::Error.3 \
		WWW::Search::Null::NoVersion.3 \
		WWW::Search::Result.3 \
		WWW::Search::Simple.3 \
		WWW::Search::Test.3

.include <bsd.port.mk>
