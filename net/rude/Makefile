# Created by: Janos.Mohacsi@bsd.hu
# $FreeBSD$

PORTNAME=	rude
PORTVERSION=	0.70
PORTREVISION=	4
CATEGORIES=	net
MASTER_SITES=	SF/${PORTNAME}/${PORTNAME}/${PORTNAME}-${PORTVERSION}

MAINTAINER=	jmohacsi@bsd.hu
COMMENT=	Rude is a Real-time UDP Data Emitter and Collector (crude)

RUN_DEPENDS=	p5-Tk>=0:${PORTSDIR}/x11-toolkits/p5-Tk

HAS_CONFIGURE=	yes
CONFIGURE_ENV=	--with-debug-lvl=3
USE_PERL5=	yes
WRKSRC=		${WRKDIR}/${PORTNAME}

MAN8=		rude.8 crude.8

DOC_FILES=	README README.rude README.crude TODO example.cfg
EXAMPLE_FILES=	crude_jitter.pl crude_parse.pl dump2trace.pl

post-install:
	${INSTALL_SCRIPT} ${WRKSRC}/grude/grude ${PREFIX}/bin
.ifndef(NOPORTDOCS)
	@${MKDIR} ${DOCSDIR}
.for FILE in ${DOC_FILES}
	@${INSTALL_DATA} ${WRKSRC}/DOC/${FILE} ${DOCSDIR}
.endfor
.for FILE in ${EXAMPLE_FILES}
	@${INSTALL_DATA} ${WRKSRC}/scripts/${FILE} ${DOCSDIR}
.endfor
.endif

.include <bsd.port.mk>
