# Created by: Sergey Skvortsov <skv@protey.ru>
# $FreeBSD$

PORTNAME=	Devel-RingBuffer
PORTVERSION=	0.31
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Shared memory ring buffers for Perl scripts diagnosis/debug

RUN_DEPENDS=	p5-IPC-Mmap>=0:${PORTSDIR}/devel/p5-IPC-Mmap
BUILD_DEPENDS:=	${RUN_DEPENDS}

USES=		perl5
USE_PERL5=	configure

MAN3=		Devel::RingBuffer.3 Devel::RingBuffer::Ring.3

.include <bsd.port.mk>
