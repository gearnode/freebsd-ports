PORTNAME=	molecule
PORTVERSION=	3.6.1
CATEGORIES=	devel python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	bofh@FreeBSD.org
COMMENT=	Aid for the development and testing of Ansible roles

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}setuptools_scm_git_archive>=1.0:devel/py-setuptools_scm_git_archive@${PY_FLAVOR}
# click-help-colors >= 0.9
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}ansible-compat>=1.0.0:sysutils/py-ansible-compat@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}Cerberus>=1.3.1:devel/py-cerberus@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}click>=8.0:devel/py-click@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}cookiecutter>=1.7.3:devel/py-cookiecutter@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}enrich>=1.2.7:textproc/py-enrich@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}Jinja2>=2.11.3:devel/py-Jinja2@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}packaging>0:devel/py-packaging@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pluggy>=0.7.1:devel/py-pluggy@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}rich>-9.5.1:textproc/py-rich@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}yaml>=5.1:devel/py-yaml@${PY_FLAVOR}
# ansi2html >= 1.6.0
# pytest-cov >= 2.10.1
# pytest-mock >= 3.3.1
# pytest-testinfra >= 6.1.0
TEST_DEPENDS=	${PYTHON_PKGNAMEPREFIX}coverage>=6.2:devel/py-coverage@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}filelock>0:sysutils/py-filelock@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pexpect>=4.8.0:misc/py-pexpect@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pytest-cov>=2.9.0:devel/py-pytest-cov@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pytest-html>=3.0.0:devel/py-pytest-html@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pytest-mock>=1.10.4:devel/py-pytest-mock@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pytest-plus>=0.2:devel/py-pytest-plus@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pytest-xdist>=2.1.0:devel/py-pytest-xdist@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pytest>=6.1.2:devel/py-pytest@${PY_FLAVOR}

USES=		python:3.6+
USE_PYTHON=	autoplist concurrent distutils

# Note: we're only running the unit tests here.  Upstream acknowledges
# that functional tests are still a work in progress.
#
# Test failures. Only three tests fail:
#  test/unit/test_util.py ......FFF.......................   [ 23%]
#
# The click module demands a UTF-8 locale when used with python-3.x
TEST_ENV=	LANG=en_US.UTF-8 \
		LC_ALL=en_US.UTF-8

NO_ARCH=	yes

OPTIONS_DEFINE=		AZURE DOCKER DOCS EC2 GCE LINT
OPTIONS_DEFAULT=	LINT
AZURE_DESC=		For testing on Microsoft Azure Platform
DOCKER_DESC=		For testing on Docker Platform(Remote)
EC2_DESC=		For testing on Amazon EC2 Platform
GCE_DESC=		For testing on Google Compute Engine Platform
LINT_DESC=		For linting molecule itself
AZURE_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}azure-cli>0:sysutils/py-azure-cli@${PY_FLAVOR}
DOCKER_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}docker>=2.0.0:sysutils/py-docker@${PY_FLAVOR}
# Sphinx >= 4.5.0, < 5.0.0  # https://github.com/sphinx-doc/sphinx/issues/10112
# simplejson >= 3.17.2
# sphinx-ansible-theme >= 0.8.0, < 0.10.0
# sphinx-notfound-page >= 0.7.1
DOCS_BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}ansible-core>-2.12.0:sysutils/py-ansible-core@${PY_FLAVOR} \
			${PYTHON_PKGNAMEPREFIX}simplejson>=3.17.2:devel/py-simplejson@${PY_FLAVOR} \
			${PYTHON_PKGNAMEPREFIX}sphinx>=4.3.1:textproc/py-sphinx@${PY_FLAVOR}
EC2_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}boto3>0:www/py-boto3@${PY_FLAVOR} \
			${PYTHON_PKGNAMEPREFIX}boto>0:devel/py-boto@${PY_FLAVOR}
GCE_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}libcloud>0:net/py-libcloud@${PY_FLAVOR}
# lint =
LINT_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}flake8>=3.8.4:devel/py-flake8@${PY_FLAVOR} \
			${PYTHON_PKGNAMEPREFIX}pre-commit>=1.21.0:devel/py-pre-commit@${PY_FLAVOR} \
			${PYTHON_PKGNAMEPREFIX}yamllint>0:devel/py-yamllint@${PY_FLAVOR}

do-test:
	@(cd ${TEST_WRKSRC} && ${SETENV} ${TEST_ENV} ${PYTHON_CMD} -m pytest)

.include <bsd.port.mk>
