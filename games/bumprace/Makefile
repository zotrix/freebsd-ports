# Created by: Dmitry Marakasov <amdmi3@amdmi3.ru>
# $FreeBSD$

PORTNAME=	bumprace
PORTVERSION=	1.5.3
PORTREVISION=	8
CATEGORIES=	games
MASTER_SITES=	http://user.cs.tu-berlin.de/~karlb/bumprace/ \
		http://mirror.amdmi3.ru/distfiles/

MAINTAINER=	amdmi3@FreeBSD.org
COMMENT=	Simple arcade racing game

GNU_CONFIGURE=	yes
USE_GMAKE=	yes
USE_SDL=	sdl mixer image

CPPFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib

PORTDOCS=	FAQ README

.include <bsd.port.options.mk>

post-patch:
	@${REINPLACE_CMD} -e '/LIBS/ s|-lSDL_[a-z]*|& $${SDL_LIBS}|' ${WRKSRC}/configure

.if ${PORT_OPTIONS:MDOCS}
post-install:
	${MKDIR} ${DOCSDIR}
.for f in ${PORTDOCS}
	${INSTALL_DATA} ${WRKSRC}/${f} ${DOCSDIR}
.endfor
.endif

.include <bsd.port.mk>
