PORTNAME=	lz4
PORTVERSION=	2.1.10
CATEGORIES=	archivers python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	python@FreeBSD.org
COMMENT=	Python binding for the LZ4 compression library

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	liblz4>=1.7.5:archivers/liblz4 \
		${PYTHON_PKGNAMEPREFIX}pkgconfig>=0:devel/py-pkgconfig@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}setuptools_scm>0:devel/py-setuptools_scm@${PY_FLAVOR}
LIB_DEPENDS=	liblz4.so:archivers/liblz4
TEST_DEPENDS=	${PYTHON_PKGNAMEPREFIX}psutil>=0:sysutils/py-psutil@${PY_FLAVOR}

USES=		python:3.6+
USE_PYTHON=	distutils pytest

post-install:
	${STRIP_CMD} ${STAGEDIR}${PYTHONPREFIX_SITELIBDIR}/${PORTNAME}/_version*.so \
		${STAGEDIR}${PYTHONPREFIX_SITELIBDIR}/${PORTNAME}/block/_block*.so \
		${STAGEDIR}${PYTHONPREFIX_SITELIBDIR}/${PORTNAME}/frame/_frame*.so

.include <bsd.port.mk>
