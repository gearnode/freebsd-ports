PORTNAME=	lava
DISTVERSION=	1.6.10
CATEGORIES=	math
DISTNAME=	${PORTNAME}_${DISTVERSION}

MAINTAINER=	tota@FreeBSD.org
COMMENT=	Latent Variable Models

LICENSE=	GPLv3

CRAN_DEPENDS=	R-cran-future.apply>0:devel/R-cran-future.apply \
		R-cran-progressr>0:devel/R-cran-progressr \
		R-cran-numDeriv>0:math/R-cran-numDeriv \
		R-cran-SQUAREM>0:math/R-cran-SQUAREM
BUILD_DEPENDS=	${CRAN_DEPENDS}
RUN_DEPENDS=	${CRAN_DEPENDS}

USES=		cran:auto-plist

.include <bsd.port.mk>
