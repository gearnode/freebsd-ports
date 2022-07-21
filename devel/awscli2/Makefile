PORTNAME=	awscli2
PORTVERSION=	2.7.17
CATEGORIES=	devel

MAINTAINER=	bryan@frimin.fr
COMMENT=	Universal Command Line Interface for Amazon Web Services

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}colorama>=0.2.5:devel/py-colorama@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}docutils>=0.10:textproc/py-docutils@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}cryptography>=3.3.2:security/py-cryptography@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}ruamel.yaml>=0.15.0:devel/py-ruamel.yaml@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}wcwidth<0.2.0:devel/py-wcwidth@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}prompt-toolkit>=3.0.24:devel/py-prompt-toolkit@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}distro>=1.7:sysutils/py-distro@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}awscrt>=0.13:devel/py-awscrt@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}dateutil>=2.1:devel/py-dateutil@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}jmespath>=0.7.1:devel/py-jmespath@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}urllib3>=1.25:net/py-urllib3@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}sqlite3>=3.9:databases/py-sqlite3@${PY_FLAVOR}

USES=	python

USE_PYTHON=	autoplist distutils concurrent

USE_GITHUB=	yes
GH_ACCOUNT=	aws
GH_PROJECT=	aws-cli

NO_ARCH=	yes
NO_BUILD=	yes

CONFLICTS_INSTALL=	awscli

.include <bsd.port.mk>
