PORTNAME=	fenics-basix
DISTVERSIONPREFIX=	v
DISTVERSION=	0.4.2
CATEGORIES=	math

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	FEniCS finite element basis evaluation library

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/../LICENSE

BUILD_DEPENDS=	xtensor>0:math/xtensor \
		xtl-quant-stack>0:devel/xtl-quant-stack
LIB_DEPENDS=	libopenblas.so:math/openblas

USES=		cmake compiler:c++17-lang

USE_GITHUB=	yes
GH_ACCOUNT=	FEniCS
GH_PROJECT=	basix

WRKSRC_SUBDIR=	cpp

.include <bsd.port.mk>
