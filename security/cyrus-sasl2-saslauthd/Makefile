# $FreeBSD$

PORTNAME=	saslauthd
PORTVERSION=	2.1.26
#PORTREVISION=	0
CATEGORIES=	security ipv6
MASTER_SITES=	ftp://ftp.cyrusimap.org/cyrus-sasl/
PKGNAMEPREFIX=	cyrus-sasl-
DISTNAME=	${PKGNAMEPREFIX}${PORTVERSION}

MAINTAINER=	ume@FreeBSD.org
COMMENT=	SASL authentication server for cyrus-sasl2

LICENSE=	BSD
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	sasl2:${PORTSDIR}/security/cyrus-sasl2

CYRUS_SASL2_DIR=${MASTERDIR}/../cyrus-sasl2
DISTINFO_FILE=	${CYRUS_SASL2_DIR}/distinfo
PATCHDIR=	${CYRUS_SASL2_DIR}/files
INSTALL_WRKSRC=	${WRKSRC}/saslauthd
DOCSDIR=	${PREFIX}/share/doc/cyrus-sasl2


# This doesn't work due to absence of .al support in our libtool
#USE_AUTOTOOLS=	libtool
#LIBTOOLFILES=	${CONFIGURE_SCRIPT} saslauthd/configure

MAN8=		saslauthd.8

USE_RC_SUBR=	saslauthd

USE_OPENSSL=	yes
GNU_CONFIGURE=	yes

CONFIGURE_ARGS=	--sysconfdir=${PREFIX}/etc \
		--with-plugindir=${PREFIX}/lib/sasl2 \
		--with-dbpath=${PREFIX}/etc/sasldb2 \
		--with-lib-subdir=lib \
		--includedir=${PREFIX}/include \
		--enable-static \
		--enable-login \
		--enable-auth-sasldb \
		--with-rc4=openssl \
		--with-saslauthd=${SASLAUTHD_RUNPATH} \
		--disable-krb4
CONFIGURE_ENV+=	andrew_cv_runpath_switch=none

OPTIONS_DEFINE=		BDB OPENLDAP HTTPFORM
OPENLDAP_DESC=		Use OpenLDAP
HTTPFORM_DESC=		Enable HTTP form authentication

.include <bsd.port.pre.mk>

.if ${PORT_OPTIONS:MBDB}
USE_BDB=	yes
INVALID_BDB_VER=2
CONFIGURE_ARGS+=--with-dblib=berkeley \
		--with-bdb-libdir=${BDB_LIB_DIR} \
		--with-bdb-incdir=${BDB_INCLUDE_DIR} \
		--with-bdb=${BDB_LIB_NAME}
.else
CONFIGURE_ARGS+=--with-dblib=ndbm
.endif

.if ${PORT_OPTIONS:MOPENLDAP}
.if defined(WITH_OPENLDAP_VER)
WANT_OPENLDAP_VER=	${WITH_OPENLDAP_VER}
.endif
USE_OPENLDAP=	yes
CONFIGURE_ARGS+=--with-ldap=${LOCALBASE}
.endif

.if ${PORT_OPTIONS:MHTTPFORM}
CONFIGURE_ARGS+=--enable-httpform
.endif

.if !defined(WITHOUT_GSSAPI) && defined(KRB5_HOME) && exists(${KRB5_HOME}/lib/libgssapi_krb5.so)
CONFIGURE_ARGS+=--enable-gssapi=${KRB5_HOME} --with-gss_impl=mit
LDFLAGS+=	-R${KRB5_HOME}/lib
.elif !defined(WITHOUT_GSSAPI) && defined(HEIMDAL_HOME) && exists(${HEIMDAL_HOME}/lib/libgssapi.a)
CONFIGURE_ARGS+=--enable-gssapi=${HEIMDAL_HOME} --with-gss_impl=heimdal
.elif !defined(WITHOUT_GSSAPI) && exists(/usr/lib/libkrb5.a)
CONFIGURE_ARGS+=--enable-gssapi=/usr
CFLAGS+=	-nostdinc -I/usr/include
.else
CONFIGURE_ARGS+=--disable-gssapi
.endif

.if ${OPENSSLBASE} == /usr
CONFIGURE_ARGS+=--with-openssl=yes
.else
CONFIGURE_ARGS+=--with-openssl=${OPENSSLBASE}
.endif

SASLAUTHD_RUNPATH?=	/var/run/saslauthd
.if ${SASLAUTHD_RUNPATH} != /var/run/saslauthd
RUNPATH=	"@comment "
.endif

CYRUS_USER?=	cyrus

DOCS=		AUTHORS COPYING ChangeLog INSTALL LDAP_SASLAUTHD NEWS README

PLIST_SUB=	PREFIX=${PREFIX} \
		DOCSDIR=${DOCSDIR:S/^${PREFIX}\///} \
		RUNPATH=${RUNPATH}

SUB_LIST+=	SASLAUTHD_RUNPATH=${SASLAUTHD_RUNPATH}

do-build:
	cd ${WRKSRC}/include && ${MAKE}
	cd ${WRKSRC}/sasldb && ${MAKE}
	cd ${WRKSRC}/saslauthd && ${MAKE}
	cd ${WRKSRC}/saslauthd && ${MAKE} saslcache
	cd ${WRKSRC}/saslauthd && ${MAKE} testsaslauthd

post-install:
	@${INSTALL_PROGRAM} ${WRKSRC}/saslauthd/saslcache \
		${PREFIX}/sbin/saslcache
	@${INSTALL_PROGRAM} ${WRKSRC}/saslauthd/testsaslauthd \
		${PREFIX}/sbin/testsaslauthd
.if ${SASLAUTHD_RUNPATH} != /var/run/saslauthd
	@${ECHO_MSG} ""
	@${ECHO_MSG} "SASLAUTHD_RUNPATH was specified."
	@${ECHO_MSG} "Make sure you create ${SASLAUTHD_RUNPATH}."
	@${ECHO_MSG} ""
.else
	${MKDIR} -m 770 ${SASLAUTHD_RUNPATH}
	${CHOWN} ${CYRUS_USER}:mail ${SASLAUTHD_RUNPATH}
.endif
.if ${PORT_OPTIONS:MDOCS}
	@${MKDIR} ${DOCSDIR}/saslauthd
.for file in ${DOCS}
	@${INSTALL_DATA} ${WRKSRC}/saslauthd/${file} ${DOCSDIR}/saslauthd
.endfor
.endif
	@PKG_PREFIX=${PREFIX} BATCH=${BATCH} ${SH} ${PKGINSTALL} ${PKGNAME} \
		POST-INSTALL
	@${CAT} ${PKGMESSAGE}

.include <bsd.port.post.mk>
