# Created by: Kurt Lidl <kurt.lidl@cello.com>
# $FreeBSD$

PORTNAME=	Data-Rx
PORTVERSION=	0.200004
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Perl implementation of Rx schema system

BUILD_DEPENDS=	p5-File-Find-Rule>=0:${PORTSDIR}/devel/p5-File-Find-Rule \
		p5-JSON>=2:${PORTSDIR}/converters/p5-JSON \
		p5-Number-Tolerant>=0:${PORTSDIR}/devel/p5-Number-Tolerant
RUN_DEPENDS:=	${BUILD_DEPENDS}
TEST_DEPENDS=	p5-Sub-Exporter>=0:${PORTSDIR}/devel/p5-Sub-Exporter \
		p5-Test-Deep>=0:${PORTSDIR}/devel/p5-Test-Deep \
		p5-Try-Tiny>=0:${PORTSDIR}/lang/p5-Try-Tiny

USES=		perl5
USE_PERL5=	configure

MAN3=		Data::Rx.3 \
		Data::Rx::CommonType.3 \
		Data::Rx::CommonType::EasyNew.3 \
		Data::Rx::CoreType.3 \
		Data::Rx::CoreType::all.3 \
		Data::Rx::CoreType::any.3 \
		Data::Rx::CoreType::arr.3 \
		Data::Rx::CoreType::bool.3 \
		Data::Rx::CoreType::def.3 \
		Data::Rx::CoreType::fail.3 \
		Data::Rx::CoreType::int.3 \
		Data::Rx::CoreType::map.3 \
		Data::Rx::CoreType::nil.3 \
		Data::Rx::CoreType::num.3 \
		Data::Rx::CoreType::one.3 \
		Data::Rx::CoreType::rec.3 \
		Data::Rx::CoreType::seq.3 \
		Data::Rx::CoreType::str.3 \
		Data::Rx::Failure.3 \
		Data::Rx::FailureSet.3 \
		Data::Rx::TypeBundle.3 \
		Data::Rx::TypeBundle::Core.3 \
		Data::Rx::Util.3

.include <bsd.port.mk>
