PORTNAME=	dbeacon
PORTVERSION=	0.3.9.1
CATEGORIES=	net
MASTER_SITES=	https://BSDforge.com/projects/source/net/dbeacon/

MAINTAINER=	portmaster@BSDforge.com
COMMENT=	Distributed multicast beacon server

LICENSE=	GPLv2+

USES=		gmake
USE_CXXSTD=	c++98

PLIST_FILES=	bin/dbeacon man/man1/dbeacon.1.gz
USE_RC_SUBR=	dbeacon

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/${PORTNAME} ${STAGEDIR}${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/docs/dbeacon.1 ${STAGEDIR}${MANPREFIX}/man/man1

.include <bsd.port.mk>
