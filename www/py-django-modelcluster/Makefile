PORTNAME=	django-modelcluster
PORTVERSION=	6.0
PORTREVISION=	1
CATEGORIES=	www python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Django extension for working with clusters of models as a single unit

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}django32>=2.2:www/py-django32@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pytz>=2015.2,1:devel/py-pytz@${PY_FLAVOR}

USES=		python:3.7+
USE_PYTHON=	autoplist concurrent distutils

NO_ARCH=	yes

OPTIONS_DEFINE=	TAGGIT
TAGGIT_DESC=	Tagging support

TAGGIT_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}django-taggit>=0.20:www/py-django-taggit@${PY_FLAVOR}

.include <bsd.port.mk>
