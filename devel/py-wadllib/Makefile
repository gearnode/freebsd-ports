PORTNAME=	wadllib
DISTVERSION=	1.3.6
CATEGORIES=	devel python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	fullermd@over-yonder.net
COMMENT=	Navigate HTTP resources using WADL files as guides

LICENSE=	LGPL3
LICENSE_FILE=	${WRKSRC}/COPYING.txt

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}lazr.uri>=0:devel/py-lazr.uri@${PY_FLAVOR}

USES=		python:3.6+
USE_PYTHON=	autoplist distutils

NO_ARCH=	yes

.include <bsd.port.mk>
