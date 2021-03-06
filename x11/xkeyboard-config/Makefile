# $FreeBSD$

PORTNAME=	xkeyboard-config
PORTVERSION=	2.9
CATEGORIES=	x11

MAINTAINER=	x11@FreeBSD.org
COMMENT=	X Keyboard Configuration Database
MASTER_SITE_SUBDIR=	individual/${XORG_CAT}/${PORTNAME}

LICENSE=	MIT

BUILD_DEPENDS=	xkbcomp:${PORTSDIR}/x11/xkbcomp
XORG_CAT=	data

USE_BZIP2=	yes
USE_GMAKE=	yes
USE_GNOME=	intlhack libxslt:build
USES=		pathfix perl5
USE_PERL5=	build
GNU_CONFIGURE=	yes
MAKE_JOBS_UNSAFE=yes

CONFIGURE_ARGS=	--with-xkb-base=${PREFIX}/share/X11/xkb \
		--with-xkb-rules-symlink=xorg
CPPFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib

MAN7=		xkeyboard-config.7

.include <bsd.port.options.mk>

# !nls case doesn't work correctly, comment it out.
#.if ${PORT_OPTIONS:MNLS}
USES+=		gettext iconv
PLIST_SUB+=	NLS=""
#.else
#CONFIGURE_ARGS+=--disable-nls
#PLIST_SUB+=	NLS="@comment "
#.endif

post-patch:
	@${REINPLACE_CMD} -e 's|/bin/bash|/bin/sh|g' -e 's|==|=|g' \
		${WRKSRC}/rules/merge.sh

post-install:
	${MKDIR} /var/lib/xkb
	${LN} -sf /var/lib/xkb ${PREFIX}/share/X11/xkb/compiled

.include <bsd.port.mk>
