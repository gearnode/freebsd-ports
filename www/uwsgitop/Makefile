PORTNAME=	uwsgitop
PORTVERSION=	0.10
PORTREVISION=	1
CATEGORIES=	www
MASTER_SITES=	CHEESESHOP

MAINTAINER=	demon@FreeBSD.org
COMMENT=	uWSGI top-like app

USES=		python:3.6+
USE_PYTHON=	distutils concurrent optsuffix

PLIST_FILES=	bin/uwsgitop %%DOCSDIR%%/README.rst

post-install:
		${MKDIR} ${STAGEDIR}${DOCSDIR}
		${INSTALL_DATA} ${WRKSRC}/README.rst ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
