PORTNAME=	capstone
PORTVERSION=	4.0.2
CATEGORIES=	devel python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DIST_SUBDIR=	python # Conflicts with devel/capstone distfile

MAINTAINER=	bofh@FreeBSD.org
COMMENT=	Python bindings for the Capstone Disassembly Engine

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE.TXT

LIB_DEPENDS=	libcapstone.so:devel/capstone4

USES=		cpe python:3.6+
CPE_VENDOR=	${PORTNAME}-engine
USE_PYTHON=	autoplist distutils
MAKE_ENV+=	LIBCAPSTONE_PATH= # Prevent bundled libcapstone from being built

NO_ARCH=	yes

post-patch:
	@${REINPLACE_CMD} 's|%%LOCALBASE%%|${LOCALBASE}|' ${WRKSRC}/capstone/__init__.py

.include <bsd.port.mk>
