PORTNAME=	jbigkit
PORTVERSION=	2.0
DISTVERSIONSUFFIX=	-11.el7
PORTREVISION=	2
CATEGORIES=	graphics linux
PKGNAMESUFFIX=	-libs

MAINTAINER=	emulation@FreeBSD.org
COMMENT=	Lossless compression for bi-level images (Linux CentOS ${LINUX_DIST_VER})

USES=		linux:c7
USE_LDCONFIG=	yes
USE_LINUX_RPM=	yes

LIB_DISTNAMES=	${PORTNAME}${PKGNAMESUFFIX}-${DISTVERSIONFULL}

DESCR=		${.CURDIR}/../${PORTNAME}/pkg-descr
DOCSDIR=	${PREFIX}/usr/share/doc/${PORTNAME}${PKGNAMESUFFIX}-${PORTVERSION}

OPTIONS_DEFINE=	DOCS

.include <bsd.port.mk>
