PORTNAME=	liblockfile
PORTVERSION=	1.17
DISTVERSIONPREFIX=	v
CATEGORIES=	devel

MAINTAINER=	yasu@FreeBSD.org
COMMENT=	Standard lockfile library

LICENSE=	GPLv2+ LGPL21+
LICENSE_COMB=	multi
LICENSE_FILE_GPLv2+ =	${WRKSRC}/licenses/GPL-2
LICENSE_FILE_LGPL21+ =	${WRKSRC}/licenses/LGPL-2

USE_GITHUB=	yes
GH_ACCOUNT=	miquels
USE_LDCONFIG=	yes

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--enable-shared \
		--with-mailgroup

PORTDOCS=	Changelog README

OPTIONS_DEFINE=	DOCS

post-install:
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/dotlockfile
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/lib/liblockfile.so.1.0

post-install-DOCS-on:
	${MKDIR} ${STAGEDIR}/${DOCSDIR}
.for f in ${PORTDOCS}
	${INSTALL_DATA} ${WRKSRC}/${f} ${STAGEDIR}${DOCSDIR}
.endfor

.include <bsd.port.mk>
