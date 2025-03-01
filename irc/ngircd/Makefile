PORTNAME=	ngircd
PORTVERSION=	26.1
PORTEPOCH=	1
CATEGORIES=	irc
MASTER_SITES=	https://ngircd.barton.de/pub/ngircd/ \
		https://ngircd.mirror.3rz.de/pub/ngircd/

MAINTAINER=	fgsch@lodoss.net
COMMENT=	Free open source daemon for Internet Relay Chat (IRC)

LICENSE=	GPLv2+
LICENSE_FILE=	${WRKSRC}/COPYING

USES=		cpe localbase:ldflags tar:xz
GNU_CONFIGURE=	yes
USE_RC_SUBR=	ngircd

CPE_VENDOR=	barton
CPE_VERSION=	${PORTVERSION:C/^([0-9]+)$/\1.0/}

PORTDOCS=	*
PLIST_FILES=	etc/ngircd.conf.sample \
		man/man5/ngircd.conf.5.gz \
		man/man8/ngircd.8.gz \
		sbin/ngircd

OPTIONS_DEFINE=		DEBUG DOCS ICONV IDENT IPV6 IRCPLUS LIBWRAP PAM \
			SNIFFER SYSLOG ZLIB
OPTIONS_RADIO=		TLS
OPTIONS_RADIO_TLS=	GNUTLS OPENSSL
OPTIONS_DEFAULT=	ICONV IRCPLUS LIBWRAP OPENSSL PAM SYSLOG ZLIB

DEBUG_CONFIGURE_ENABLE=		debug
GNUTLS_LIB_DEPENDS=		libgnutls.so:security/gnutls
GNUTLS_CONFIGURE_WITH=		gnutls
ICONV_USES=			iconv
ICONV_CONFIGURE_WITH=		iconv
IDENT_DESC=			IDENT (AUTH) protocol support
IDENT_LIB_DEPENDS=		libident.so:security/libident
IDENT_CONFIGURE_WITH=		ident
IPV6_CONFIGURE_ENABLE=		ipv6
IRCPLUS_DESC=			IRC+ protocol
IRCPLUS_CONFIGURE_ENABLE=	ircplus
LIBWRAP_CONFIGURE_WITH=		tcp-wrappers
OPENSSL_USES=			ssl
OPENSSL_CONFIGURE_WITH=		openssl
PAM_CONFIGURE_WITH=		pam
SNIFFER_DESC=			IRC traffic sniffer
SNIFFER_CONFIGURE_ENABLE=	sniffer
SYSLOG_CONFIGURE_WITH=		syslog
ZLIB_CONFIGURE_WITH=		zlib

post-patch:
	@${REINPLACE_CMD} -e \
		'/LIBS/s|-liconv|${ICONV_LIB}|' ${WRKSRC}/configure
	@${REINPLACE_CMD} -e \
		'/toplevel/s| \.\./COPYING|| ; \
		 /INSTALL/s|.conf$$|.conf.sample|' ${WRKSRC}/doc/Makefile.in

.include <bsd.port.mk>
