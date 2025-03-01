PORTNAME=	netxms
PORTVERSION=	2.2.2
CATEGORIES=	net-mgmt
MASTER_SITES=	http://www.netxms.org/download/releases/${PORTVERSION:R}/${PORTVERSION}/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Network monitoring system

LICENSE=	GPLv2 LGPL21
LICENSE_COMB=	multi

BROKEN_FreeBSD_12=	'net/iso88025.h' file not found
BROKEN_FreeBSD_13=	'net/iso88025.h' file not found
BROKEN_FreeBSD_14=	'net/iso88025.h' file not found

LIB_DEPENDS=	libcurl.so:ftp/curl \
		libexpat.so:textproc/expat2 \
		libjansson.so:devel/jansson \
		libtre.so:textproc/libtre \
		libmosquitto.so:net/mosquitto

OPTIONS_DEFINE=	SERVER CLIENT AGENT SSH
OPTIONS_DEFAULT=	CLIENT AGENT SSH
OPTIONS_SINGLE=	SERVER
OPTIONS_SINGLE_SERVER=	MYSQL PGSQL ODBC
OPTIONS_SUB=	yes

SERVER_DESC=	Install NetXMS server & agent
CLIENT_DESC=	Install NetXMS client
AGENT_DESC=	Install NetXMS agent

CLIENT_CONFIGURE_ON=	--with-client
AGENT_CONFIGURE_ON=	--with-agent
SERVER_CONFIGURE_ON=	--with-server
MYSQL_CONFIGURE_ON=	--with-mysql
MYSQL_USES=		mysql
PGSQL_CONFIGURE_ON=	--with-pgsql
PGSQL_USES=		pgsql
ODBC_CONFIGURE_ON=	--with-odbc
ODBC_LIB_DEPENDS=	libodbc.so:databases/unixODBC
SSH_CONFIGURE_OFF=	--disable-ssh
SSH_LIB_DEPENDS=	libssh.so:security/libssh

USES=		gmake iconv libtool perl5 ssl
GNU_CONFIGURE=	yes
USE_LDCONFIG=	yes
INSTALL_TARGET=	install-strip

CPPFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib

USERS=		netxms
GROUPS=		netxms

.include <bsd.port.options.mk>

.if ${PORT_OPTIONS:MSERVER} || ${PORT_OPTIONS:MCLIENT}
PLIST_SUB+=	NXMAP=""
.else
PLIST_SUB+=	NXMAP="@comment "
.endif

.if ${PORT_OPTIONS:MSERVER} || ${PORT_OPTIONS:MAGENT}
PLIST_SUB+=	NXCP=""
.else
PLIST_SUB+=	NXCP="@comment "
.endif

.if ${PORT_OPTIONS:MSERVER}
USE_RC_SUBR+=	netxmsd
.if !${PORT_OPTIONS:MAGENT}
USE_RC_SUBR+=	nxagentd
.endif
.endif

.if ${PORT_OPTIONS:MAGENT}
USE_RC_SUBR+=	nxagentd
.endif

post-patch:
	@${REINPLACE_CMD} 's/-liconv/${ICONV_LIB}/' ${WRKSRC}/configure

post-install:
.if ${PORT_OPTIONS:MSERVER}
.if !exists(${STAGEDIR}${PREFIX}/etc/netxmsd.conf.sample)
	${CP} ${WRKSRC}/contrib/netxmsd.conf-dist ${STAGEDIR}${PREFIX}/etc/netxmsd.conf.sample
.endif
.endif
.if ${PORT_OPTIONS:MSERVER} || ${PORT_OPTIONS:MAGENT}
.if !exists(${STAGEDIR}${PREFIX}/etc/nxagentd.conf.sample)
	${CP} ${WRKSRC}/contrib/nxagentd.conf-dist ${STAGEDIR}${PREFIX}/etc/nxagentd.conf.sample
.endif
.endif

.include <bsd.port.mk>
