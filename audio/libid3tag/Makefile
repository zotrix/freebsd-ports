# Created by: Sergey Akifyev <asa@gascom.ru>
# $FreeBSD$

PORTNAME=	libid3tag
PORTVERSION=	0.15.1b
CATEGORIES=	audio
MASTER_SITES=	SF/mad/${PORTNAME}/${PORTVERSION} \
		ftp://ftp.mars.org/pub/mpeg/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	ID3 tags library (part of MAD project)

LICENSE=	GPLv2

USE_GNOME=	pkgconfig
GNU_CONFIGURE=	yes
USE_LDCONFIG=	yes

post-patch:
	@${REINPLACE_CMD} -e 's|echo aout|echo elf|g' \
	    	${WRKSRC}/configure

post-build:
	cd ${WRKSRC} && CONFIG_FILES=id3tag.pc CONFIG_HEADERS= ${SH} ./config.status

post-install:
	${MKDIR} ${PREFIX}/libdata/pkgconfig
	${INSTALL_DATA} ${WRKSRC}/id3tag.pc ${PREFIX}/libdata/pkgconfig

.include <bsd.port.mk>
