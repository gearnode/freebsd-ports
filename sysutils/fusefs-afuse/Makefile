PORTNAME=	afuse
PORTVERSION=	0.4.1
PORTREVISION=	1
CATEGORIES=	sysutils
MASTER_SITES=	https://BSDforge.com/projects/source/sysutils/afuse/
PKGNAMEPREFIX=	fusefs-

MAINTAINER=	portmaster@BSDforge.com
COMMENT=	File system automounting implemented in user-space using FUSE

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

USES=		cpe fuse pkgconfig
GNU_CONFIGURE=	yes

PORTDOCS=	AUTHORS README

OPTIONS_DEFINE=	DOCS
DOCS_SUB_FILES=	pkg-message

post-install:
	${INSTALL_MAN} ${FILESDIR}/afuse.1 ${STAGEDIR}${MAN1PREFIX}/man/man1

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${PORTDOCS:S,^,${WRKSRC}/,} ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
