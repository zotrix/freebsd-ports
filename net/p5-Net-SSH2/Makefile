# Created by: Jin-Shan Tseng <tjs@cdpa.nsysu.edu.tw>
# $FreeBSD$

PORTNAME=	Net-SSH2
PORTVERSION=	0.51
CATEGORIES=	net perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	jadawin@FreeBSD.org
COMMENT=	Support for the SSH 2 protocol via libSSH2

LICENSE=	ART10 GPLv1
LICENSE_COMB=	dual

LIB_DEPENDS=	ssh2.1:${PORTSDIR}/security/libssh2

USES=	perl5
USE_PERL5=	configure

MAN3=		Net::SSH2.3 Net::SSH2::Channel.3 \
		Net::SSH2::Dir.3 Net::SSH2::File.3 \
		Net::SSH2::Listener.3 Net::SSH2::PublicKey.3 \
		Net::SSH2::SFTP.3

.include <bsd.port.mk>
