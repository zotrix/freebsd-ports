# Created by: bapt <baptiste.daroussin@gmail.com>
# $FreeBSD$

PORTNAME=	Mixin-Linewise
PORTVERSION=	0.003
PORTREVISION=	1
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:RJBS
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Write your linewise code for handles; this does the rest

LICENSE=	ART10 GPLv1
LICENSE_COMB=	dual

BUILD_DEPENDS+=	p5-Sub-Exporter>=0.900:${PORTSDIR}/devel/p5-Sub-Exporter \
	p5-IO-String>=0:${PORTSDIR}/devel/p5-IO-String
RUN_DEPENDS+=	p5-Sub-Exporter>=0.900:${PORTSDIR}/devel/p5-Sub-Exporter \
	p5-IO-String>=0:${PORTSDIR}/devel/p5-IO-String

USES=		perl5
USE_PERL5=	configure

MAN3=		Mixin::Linewise::Readers.3 \
		Mixin::Linewise::Writers.3 \
		Mixin::Linewise.3
PLIST_FILES+=	%%SITE_PERL%%/Mixin/Linewise/Readers.pm \
		%%SITE_PERL%%/Mixin/Linewise/Writers.pm \
		%%SITE_PERL%%/Mixin/Linewise.pm \
		%%SITE_PERL%%/%%PERL_ARCH%%/auto/Mixin/Linewise/.packlist
PLIST_DIRS+=	%%SITE_PERL%%/Mixin/Linewise \
		%%SITE_PERL%%/Mixin \
		%%SITE_PERL%%/%%PERL_ARCH%%/auto/Mixin/Linewise \
		%%SITE_PERL%%/%%PERL_ARCH%%/auto/Mixin

.include <bsd.port.mk>
