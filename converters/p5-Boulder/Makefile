# Created by: Andreas Klemm <andreas@klemm.gtn.com>
# $FreeBSD$

PORTNAME=	Boulder
PORTVERSION=	1.30
CATEGORIES=	converters perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	tobez@FreeBSD.org
COMMENT=	An API for hierarchical tag/value structures

BUILD_DEPENDS=	p5-XML-Parser>=0:${PORTSDIR}/textproc/p5-XML-Parser
RUN_DEPENDS:=	${BUILD_DEPENDS}

USES=		perl5
USE_PERL5=	configure

MAN3=		Boulder.3 \
		Boulder::Blast.3 \
		Boulder::Blast::NCBI.3 \
		Boulder::Blast::WU.3 \
		Boulder::Genbank.3 \
		Boulder::Medline.3 \
		Boulder::LocusLink.3 \
		Boulder::Omim.3 \
		Boulder::Store.3 \
		Boulder::Stream.3 \
		Boulder::String.3 \
		Boulder::Swissprot.3 \
		Boulder::Unigene.3 \
		Boulder::XML.3 \
		Stone.3 \
		Stone::Cursor.3 \
		Stone::GB_Sequence.3

.include <bsd.port.mk>
