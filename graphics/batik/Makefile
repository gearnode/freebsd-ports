PORTNAME=	batik
PORTVERSION=	1.14
CATEGORIES=	graphics java
MASTER_SITES=	APACHE/xmlgraphics/${PORTNAME}/binaries
DISTNAME=	${PORTNAME}-bin-${PORTVERSION}

MAINTAINER=	makc@FreeBSD.org
COMMENT=	Java based SVG toolkit

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

CPE_VENDOR=	apache

USES=		cpe
USE_JAVA=	yes

NO_ARCH=	yes
NO_BUILD=	yes

WRKSRC=		${WRKDIR}/${PORTNAME}-${PORTVERSION}
JAVAJARDIR=	${JAVASHAREDIR}/${PORTNAME}

PLIST_SUB=	VERSION=${PORTVERSION}

PORTDOCS=	CHANGES NOTICE README

OPTIONS_DEFINE=	DOCS

do-install:
	(cd ${INSTALL_WRKSRC} && ${COPYTREE_SHARE} . ${STAGEDIR}${JAVAJARDIR} "-name *\.jar")
	(cd ${STAGEDIR}${JAVAJARDIR}/lib && ${LN} batik-all-${PORTVERSION}.jar batik-all.jar)

do-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	(cd ${INSTALL_WRKSRC} && ${INSTALL_DATA} ${PORTDOCS} ${STAGEDIR}${DOCSDIR})

.include <bsd.port.mk>
