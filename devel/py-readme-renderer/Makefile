PORTNAME=	readme-renderer
PORTVERSION=	35.0
CATEGORIES=	devel python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	readme_renderer-${PORTVERSION}

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Library for rendering "readme" descriptions

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}bleach>=2.1.0:www/py-bleach@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}docutils>=0.13.1,1:textproc/py-docutils@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pygments>=2.5.1:textproc/py-pygments@${PY_FLAVOR}

USES=		python:3.7+
USE_PYTHON=	autoplist concurrent distutils

NO_ARCH=	yes

OPTIONS_DEFINE=	MD
MD_DESC=	Markdown support

MD_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}cmarkgfm>=0.8.0:textproc/py-cmarkgfm@${PY_FLAVOR}

.include <bsd.port.mk>
