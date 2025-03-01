PORTNAME=	mariadb
PORTVERSION=	3.1.15
CATEGORIES=	databases
MASTER_SITES=	https://mirror.nodesdirect.com/${SITESDIR}/ \
		https://mirror.one.com/${SITESDIR}/ \
		https://ftp.nluug.nl/db/${SITESDIR}/ \
		https://ftp.icm.edu.pl/pub/unix/database/${SITESDIR}/ \
		https://mirror.truenetwork.ru/${SITESDIR}/ \
		https://mirrors.aliyun.com/${SITESDIR}/ \
		https://ftp.ubuntu-tw.org/mirror/${SITESDIR}/ \
		https://mirror.kku.ac.th/${SITESDIR}/ \
		https://espejito.fder.edu.uy/${SITESDIR}/ \
		https://mirror1.cl.netactuate.com/${SITESDIR}/ \
		https://ftp.osuosl.org/pub/${SITESDIR}/
PKGNAMESUFFIX=	-connector-odbc
DISTNAME=	${PORTNAME}${PKGNAMESUFFIX}-${DISTVERSION}-src

MAINTAINER=	brnrd@FreeBSD.org
COMMENT=	MariaDB database connector for odbc

LICENSE=	LGPL21
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libodbc.so:databases/unixODBC \
		libmariadb.so:databases/mariadb-connector-c

USES=		cmake:insource ssl
USE_LDCONFIG=	${PREFIX}/lib/mariadbconnector-odbc

SITESDIR=	${PORTNAME}/${PKGNAMESUFFIX:S/^-//}-${PORTVERSION:S/.b$//}
DOCSDIR=	${PREFIX}/share/doc/mysql

OPTIONS_DEFINE=	SSL
OPTIONS_DEFAULT=SSL

CMAKE_ARGS+=	-DCOMPILATION_COMMENT="FreeBSD Ports"
CFLAGS+=	-I${LOCALBASE}/include/mariadb
LDFLAGS+=	-L${LOCALBASE}/lib/mariadb

SSL_CMAKE_ON=	-DWITH_OPENSSL=on

PLIST_FILES=	lib/mariadb/libmaodbc.so \
		libdata/pkgconfig/libmaodbc.pc

post-install:
	${RM} -r ${STAGEDIR}${PREFIX}/share/doc/${PORTNAME}${PKGNAMESUFFIX} \
		${STAGEDIR}${PREFIX}/docs

.include <bsd.port.mk>
