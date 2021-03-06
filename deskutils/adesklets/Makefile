# New ports collection makefile for:	adesklets
# Date created:		2005-05-25
# Whom:			Roman Bogorodskiy <novel@FreeBSD.org>
#
# $FreeBSD$
#

PORTNAME=	adesklets
PORTVERSION=	0.6.1
PORTREVISION=	9
CATEGORIES=	deskutils
MASTER_SITES=	SF/${PORTNAME}/${PORTNAME}%20%28core%29/${PORTVERSION}

MAINTAINER=	novel@FreeBSD.org
COMMENT=	An interactive Imlib2 console for the X Window system

RUN_DEPENDS=	gsed:${PORTSDIR}/textproc/gsed

GNU_CONFIGURE=	yes
USE_PYTHON=	yes
USE_GMAKE=	yes
USE_BZIP2=	yes
USE_EFL=	imlib2
USES=		iconv
WANT_PERL=	yes

MAN1=		adesklets.1 \
		adesklets_checkin.1 \
		adesklets_installer.1 \
		adesklets_submit.1
INFO=		adesklets \
		adesklets_fr

SUB_FILES=	pkg-message
INSTALLS_EGGINFO=	yes
LDFLAGS+=	-liconv

.if !defined(WITHOUT_PERL)
USE_PERL5=	yes
PLIST_SUB+=	PERL=""
.else
CONFIGURE_ARGS+=	--without-perl-support
PLIST_SUB+=	PERL="@comment "
.endif

.if defined(WITHOUT_HISTORY)
CONFIGURE_ARGS+=	--without-history
.endif

pre-everything::
	@${ECHO_MSG} "You may specify the following on the command line:"
	@${ECHO_MSG} ""
	@${ECHO_MSG} "WITHOUT_PERL=yes to disable perl support"
	@${ECHO_MSG} "WITHOUT_HISTORY=yes to disable history support in interactive mode"
	@${ECHO_MSG} ""

post-extract:
	@${REINPLACE_CMD} -e 's| sed | gsed |g' ${WRKSRC}/utils/adesklets_frontend.sh.in

post-install:
	@${CAT} ${PKGMESSAGE}

.include <bsd.port.mk>
