# $FreeBSD$

PORTNAME=	dislin
PORTVERSION=	10.1
CATEGORIES=	math
MASTER_SITES=	ftp://ftp.gwdg.de/pub/grafik/dislin/unix/
DISTNAME=	${PORTNAME}-${PORTVERSION}.fbsd${BINVER}
DIST_SUBDIR=	${PORTNAME}-${PORTVERSION}_${PORTREVISION}

MAINTAINER=	sylvio@FreeBSD.org
COMMENT=	A scientific data plotting package

LIB_DEPENDS=	f2c.2:${PORTSDIR}/lang/f2c

DEPRECATED=	Broken for more than 6 month
EXPIRATION_DATE=	2013-08-27
BROKEN=		size mismatch

RESTRICTED=	free for non-commercial use.
USE_XORG=	x11
NO_BUILD=	yes
WRKSRC=		${WRKDIR}/${PORTNAME}-${PORTVERSION}

DISTINFO_FILE=	${MASTERDIR}/distinfo${BINVER}
PLIST_SUB+=	VER=${PORTVERSION} MAJ=${MAJ}
SUB_FILES=	dislin.sh pkg-message
SUB_LIST+=	DISLIN_DIR=${DISLIN_DIR}
PKGMESSAGE=	${WRKDIR}/pkg-message
DISLIN_DIR=	${PREFIX}/dislin
PROGRAMS=	clink disaps disdrv disdrv_nw disdrv_w disgcl disgif dishlp	\
		disimg disman dismov distif dlink f2clink gclhelp gclhlp gclman
LIBS=		dislin dislin_d
MAJ=		${PORTVERSION:R}

USE_LDCONFIG=	yes

.include <bsd.port.pre.mk>

.if ${OSVERSION} > 700000 && ${OSVERSION} < 800000
BINVER=
BINDIR=
PLIST_SUB+=	DISLIN7=""
.else
BINVER=		-7.0
BINDIR=		_70
PLIST_SUB+=	DISLIN7="@comment "
.endif

.if ${OSVERSION} > 800000
BINVER=
BINDIR=
PLIST_SUB+=	DISLIN8=""
.else
BINVER=		-7.0
BINDIR=		_70
PLIST_SUB+=	DISLIN8="@comment "
.endif

SCRIPTS2FIX=	clink dlink f2clink

pre-configure:
.for sc in ${SCRIPTS2FIX}
	${REINPLACE_CMD} -e '/libs="-L$$DISLIN/s|"$$| ${PTHREAD_LIBS}"|'	\
		${WRKSRC}/fbsd${BINDIR}/bin/${sc}
.endfor

do-install:
	cd ${WRKSRC} && ${SETENV} DISLIN=${DISLIN_DIR} ${SH} INSTALL
	${RM} ${SCRIPTS2FIX:S|^|${DISLIN_DIR}/bin/|:S|$|.bak|}
	${INSTALL_SCRIPT} ${WRKDIR}/dislin.sh ${DISLIN_DIR}/bin
.for _program in ${PROGRAMS}
	${LN} -s ${DISLIN_DIR}/bin/dislin.sh ${PREFIX}/bin/${_program}
.endfor
.for _lib in ${LIBS}
	${LN} -s ${DISLIN_DIR}/lib/${_lib}-${PORTVERSION}.a	\
		${PREFIX}/lib/lib${_lib}.a
	${LN} -s ${DISLIN_DIR}/lib/${_lib}-${PORTVERSION}.so	\
		${PREFIX}/lib/lib${_lib}.so.${MAJ}
.endfor
	${LN} -s ${LOCALBASE}/lib/libf2c.so ${DISLIN_DIR}/libg2c.so
	${LN} -s ${LOCALBASE}/lib/libf2c.so.2 ${DISLIN_DIR}/libg2c.so.2
	${CHOWN} -R ${SHAREOWN}:${SHAREGRP} ${DISLIN_DIR}
	${CHMOD} a+r ${DISLIN_DIR}/README

post-install:
	@${ECHO_MSG}
	@${CAT} ${PKGMESSAGE}
	@${ECHO_MSG}

.include <bsd.port.post.mk>
