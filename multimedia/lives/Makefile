# Created by: Andrew Pantyukhin <infofarmer@FreeBSD.org>
# $FreeBSD$

PORTNAME=	lives
PORTVERSION=	2.0.5
CATEGORIES=	multimedia
MASTER_SITES=	http://salsaman.home.xs4all.nl/lives/current/
DISTNAME=	LiVES-${PORTVERSION}

MAINTAINER=	pawel@FreeBSD.org
COMMENT=	Video editing system

LICENSE=	GPLv3

BUILD_DEPENDS=	${LOCALBASE}/include/linux/input.h:${PORTSDIR}/multimedia/v4l_compat \
		${LOCALBASE}/bin/analyseplugin:${PORTSDIR}/audio/ladspa
LIB_DEPENDS=	asound:${PORTSDIR}/audio/alsa-lib \
		jack:${PORTSDIR}/audio/jack \
		pulse:${PORTSDIR}/audio/pulseaudio \
		oil:${PORTSDIR}/devel/liboil \
		visual-0.4:${PORTSDIR}/graphics/libvisual04 \
		opencv_calib3d:${PORTSDIR}/graphics/opencv \
		fftw3:${PORTSDIR}/math/fftw3 \
		fftw3f:${PORTSDIR}/math/fftw3-float \
		avcodec:${PORTSDIR}/multimedia/ffmpeg \
		dv:${PORTSDIR}/multimedia/libdv \
		mjpegutils:${PORTSDIR}/multimedia/mjpegtools \
		schroedinger:${PORTSDIR}/multimedia/schroedinger
RUN_DEPENDS=	${LOCALBASE}/bin/analyseplugin:${PORTSDIR}/audio/ladspa \
		mpg123:${PORTSDIR}/audio/mpg123 \
		sox:${PORTSDIR}/audio/sox \
		ogg123:${PORTSDIR}/audio/vorbis-tools \
		convert:${PORTSDIR}/graphics/ImageMagick \
		sswf:${PORTSDIR}/graphics/sswf \
		mencoder:${PORTSDIR}/multimedia/mencoder \
		mkvmerge:${PORTSDIR}/multimedia/mkvtoolnix \
		mplayer:${PORTSDIR}/multimedia/mplayer \
		ogmmerge:${PORTSDIR}/multimedia/ogmtools \
		transcode:${PORTSDIR}/multimedia/transcode \
		x264:${PORTSDIR}/multimedia/x264 \
		xmms:${PORTSDIR}/multimedia/xmms \
		cdrecord:${PORTSDIR}/sysutils/cdrtools

WRKSRC=		${WRKDIR}/${DISTNAME:L}

USES=		pkgconfig
USE_BZIP2=	yes
GNU_CONFIGURE=	yes
USE_CSTD=	gnu89
USE_PYTHON=	yes
USE_PERL5=	yes
USE_GHOSTSCRIPT_RUN=	yes
USE_GNOME=	gtk20
USE_LDCONFIG=	yes

CONFIGURE_ARGS=	--disable-ldvgrab --disable-gtk3

CPPFLAGS+=	-I${LOCALBASE}/include -fPIC
LDFLAGS+=	-L${LOCALBASE}/lib -pthread

DOC_FILES=	AUTHORS BUGS ChangeLog FEATURES GETTING.STARTED README \
		OMC/lives-OMC.txt \
		RFX/LiVES-Perl.odt RFX/rfxbuilder.odt RFX/RFX.spec \
		docs/clip_format.txt \
		lives-plugins/marcos-encoders/README.multi_encoder \
		weed-docs/weedspec.txt weed-docs/weedevents.txt

PORT_VERBS=	lives LiVES _encoder.py midistart midistop smogrify sendOSC

OPTIONS_DEFINE=	DOCS DOXYGEN FREI0R NLS
OPTIONS_SUB=	yes

DOXYGEN_BUILD_DEPENDS=	${LOCALBASE}/bin/doxygen:${PORTSDIR}/devel/doxygen
DOXYGEN_CONFIGURE_OFF=	--disable-doxygen
FREI0R_BUILD_DEPENDS=	${LOCALBASE}/include/frei0r.h:${PORTSDIR}/graphics/frei0r
FREI0R_RUN_DEPENDS=	${LOCALBASE}/include/frei0r.h:${PORTSDIR}/graphics/frei0r
NLS_USES=		gettext
NLS_CONFIGURE_OFF=	--disable-nls

.include <bsd.port.options.mk>

.if ! ${PORT_OPTIONS:MFREI0R}
CONFIGURE_ENV+=	ac_cv_header_frei0r_h=no
.endif

post-patch:
	@${REINPLACE_CMD} -e 's| install-docDATA||g; s|-$$(VERSION)||g' \
		${WRKSRC}/Makefile.in
	@${REINPLACE_CMD} -e 's|: install-data-local |: |g; s|-ldl||' \
		${WRKSRC}/lives-plugins/weed-plugins/gdk/Makefile.in \
		${WRKSRC}/lives-plugins/weed-plugins/Makefile.in
	@${REINPLACE_CMD} -e 's|off64_t|off_t|g ; s|lseek64|lseek|g' \
		${WRKSRC}/src/audio.c \
		${WRKSRC}/lives-plugins/plugins/decoders/dv_decoder.c \
		${WRKSRC}/lives-plugins/plugins/decoders/ogg_decoder.h
	@${REINPLACE_CMD} -e 's|/usr/local/lib/|${LOCALBASE}/lib/|g' \
		${WRKSRC}/lives-plugins/weed-plugins/frei0r.c
	@${REINPLACE_CMD} 's|(libdir)/pkgconfig|(prefix)/libdata/pkgconfig|g' \
		${WRKSRC}/libweed/Makefile.in
	@${REINPLACE_CMD} 's|/bin/touch|/usr/bin/touch|g' \
		${WRKSRC}/src/callbacks.c \
		${WRKSRC}/src/saveplay.c \
		${WRKSRC}/src/utils.c
	@${REINPLACE_CMD} '/cp -rf/ s|data/|data|g; /cp -rf/ s|icons/|icons|g' \
		${WRKSRC}/lives-plugins/weed-plugins/cairo/Makefile.in \
		${WRKSRC}/lives-plugins/weed-plugins/Makefile.in

post-install:
.if ${PORT_OPTIONS:MDOCS}
	@${MKDIR} ${DOCSDIR}
	${INSTALL_DATA} ${DOC_FILES:S|^|${WRKSRC}/|} ${DOCSDIR}
.endif
.if ${PORT_OPTIONS:MDOXYGEN}
	@cd ${PREFIX} && \
	${FIND} ${DOCSDIR:S|${PREFIX}/||} ! -type d >> ${TMPPLIST} && \
	${FIND} ${DOCSDIR:S|${PREFIX}/||} -type d | ${SORT} -r | \
	${SED} 's|^|@dirrm |' >> ${TMPPLIST}
.endif

.include <bsd.port.mk>
