PORTNAME=	libdombey
PORTVERSION=	5.56
CATEGORIES=	devel
MASTER_SITES=	http://www.mammothcheese.ca/

MAINTAINER=	jimmy@mammothcheese.ca
COMMENT=	SCGI application server in a library

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=		ssl
USE_LDCONFIG=	yes
CFLAGS+=	-I${OPENSSLINC}

DESTDIRNAME=	STAGEDIR

PLIST_SUB=	PORTVERSION=${PORTVERSION}

.include <bsd.port.mk>
