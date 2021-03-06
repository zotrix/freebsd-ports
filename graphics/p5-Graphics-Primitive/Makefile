# Ports collection makefile for:	p5-Graphics-Primitive
# Created by: chinsan
# $FreeBSD$

PORTNAME=	Graphics-Primitive
PORTVERSION=	0.61
CATEGORIES=	graphics perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:GPHAT
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Device and library agnostic graphic primitives

RUN_DEPENDS=	p5-Forest>=0.06:${PORTSDIR}/devel/p5-Forest \
		p5-Geometry-Primitive>=0.16:${PORTSDIR}/graphics/p5-Geometry-Primitive \
		p5-Graphics-Color>=0.20:${PORTSDIR}/graphics/p5-Graphics-Color \
		p5-JSON-Any>=1.22:${PORTSDIR}/converters/p5-JSON-Any \
		p5-Moose>=0.90:${PORTSDIR}/devel/p5-Moose \
		p5-MooseX-Clone>=0.04:${PORTSDIR}/devel/p5-MooseX-Clone \
		p5-MooseX-Storage>=0.17:${PORTSDIR}/devel/p5-MooseX-Storage
BUILD_DEPENDS:=	${RUN_DEPENDS}

USES=		perl5
USE_PERL5=	configure

MAN3=		Graphics::Primitive.3 \
		Graphics::Primitive::Aligned.3 \
		Graphics::Primitive::Border.3 \
		Graphics::Primitive::Brush.3 \
		Graphics::Primitive::Canvas.3 \
		Graphics::Primitive::Component.3 \
		Graphics::Primitive::ComponentList.3 \
		Graphics::Primitive::Container.3 \
		Graphics::Primitive::Driver.3 \
		Graphics::Primitive::Driver::TextLayout.3 \
		Graphics::Primitive::Font.3 \
		Graphics::Primitive::Image.3 \
		Graphics::Primitive::Insets.3 \
		Graphics::Primitive::Operation.3 \
		Graphics::Primitive::Operation::Fill.3 \
		Graphics::Primitive::Operation::Stroke.3 \
		Graphics::Primitive::Oriented.3 \
		Graphics::Primitive::Paint.3 \
		Graphics::Primitive::Paint::Gradient.3 \
		Graphics::Primitive::Paint::Gradient::Linear.3 \
		Graphics::Primitive::Paint::Gradient::Radial.3 \
		Graphics::Primitive::Paint::Solid.3 \
		Graphics::Primitive::Path.3 \
		Graphics::Primitive::TextBox.3

.include <bsd.port.mk>
