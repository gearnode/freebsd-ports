PORTNAME=	bdflib
PORTVERSION=	1.0.4
PORTREVISION=	1
DISTVERSIONPREFIX=	v
CATEGORIES=	x11-fonts python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	python@FreeBSD.org
COMMENT=	Library for working with BDF font files

LICENSE=	GPLv3

USES=		python:3.6+
USE_PYTHON=	autoplist concurrent distutils

NO_ARCH=	yes

post-patch:
	@${REINPLACE_CMD} -e '/version=/ s|guess_version()|"${PORTVERSION}"|' ${WRKSRC}/setup.py

.include <bsd.port.mk>
