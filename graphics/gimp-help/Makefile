# Created by: Adam Weinberger <adamw@FreeBSD.org>
# $FreeBSD$

PORTNAME=	gimp-help
PORTVERSION=	2.6.1
CATEGORIES=	graphics
MASTER_SITES=	# empty
PKGNAMESUFFIX=	-html
DISTFILES=	# none
EXTRACT_ONLY=	# empty

MAINTAINER=	liangtai.s4@gmail.com
COMMENT=	The meta port for GIMP User Manual

LICENSE=	GFDL

.MAKE.FreeBSD_UL=	yes

NO_BUILD=	yes

LANG_ALL=	de en es fr it ja ko nl nn pl ru sv zh_CN

de_PORT=	german/gimp-help
fr_PORT=	french/gimp-help
ja_PORT=	japanese/gimp-help
ko_PORT=	korean/gimp-help
pl_PORT=	polish/gimp-help
ru_PORT=	russian/gimp-help
zh_CN_PORT=	chinese/gimp-help-zh_CN

# you can find more in ${PORTSDIR}/misc/kde4-l10n/files/kde4-lang-names
de_NAME=	German
en_NAME=	English
es_NAME=	Spanish
fr_NAME=	French
it_NAME=	Italian
ja_NAME=	Japanese
ko_NAME=	Korean
nl_NAME=	Dutch
nn_NAME=	Norwegian Nynorsk
pl_NAME=	Polish
ru_NAME=	Russian
sv_NAME=	Swedish
zh_CN_NAME=	Chinese Simplified

.for lang in ${LANG_ALL}
${lang}_DETECT?=	${LOCALBASE}/share/gimp/help/${lang}/index.html
${lang}_PORT?=		misc/gimp-help-${lang}
${lang}_NAME?=		${lang}
${lang:U}_DESC=		${${lang}_NAME}
.endfor

OPTIONS_DEFINE=	ALL
OPTIONS_DEFAULT=	ALL
ALL_DESC=	All translations
.for lang in ${LANG_ALL}
OPTIONS_DEFINE+=	${lang:U}
.endfor

.include <bsd.port.options.mk>

.for lang in ${LANG_ALL}
.if ${PORT_OPTIONS:MALL} || ${PORT_OPTIONS:M${lang:U}}
RUN_DEPENDS+=	${${lang}_DETECT}:${PORTSDIR}/${${lang}_PORT}
.endif
.endfor

do-install:
	${DO_NADA}

.include <bsd.port.mk>
