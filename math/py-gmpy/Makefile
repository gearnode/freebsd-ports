PORTNAME=	gmpy
PORTVERSION=	1.17
PORTREVISION=	1
CATEGORIES=	math python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	wen@FreeBSD.org
COMMENT=	Python Extension that Wraps the GMP Library

LIB_DEPENDS=	libgmp.so:math/gmp

USES=		python:3.6+ zip
USE_PYTHON=	distutils autoplist

post-extract:
	${REINPLACE_CMD} -e 's#/usr/local#${LOCALBASE}#g' \
		${WRKSRC}/setup.py

.include <bsd.port.mk>
