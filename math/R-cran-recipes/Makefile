PORTNAME=	recipes
PORTVERSION=	1.0.1
CATEGORIES=	math
DISTNAME=	${PORTNAME}_${PORTVERSION}

MAINTAINER=	tota@FreeBSD.org
COMMENT=	Preprocessing Tools to Create Design Matrices

LICENSE=	MIT

CRAN_DEPENDS=	R-cran-dplyr>0:math/R-cran-dplyr \
		R-cran-cli>0:devel/R-cran-cli \
		R-cran-ellipsis>0:devel/R-cran-ellipsis \
		R-cran-generics>=0.1.2:devel/R-cran-generics \
		R-cran-glue>0:devel/R-cran-glue \
		R-cran-gower>0:math/R-cran-gower \
		R-cran-hardhat>=1.2.0:devel/R-cran-hardhat \
		R-cran-ipred>=0.9.12:math/R-cran-ipred \
		R-cran-lifecycle>0:devel/R-cran-lifecycle \
		R-cran-lubridate>=1.8.0:devel/R-cran-lubridate \
		R-cran-magrittr>0:devel/R-cran-magrittr \
		R-cran-purrr>=0.2.3:devel/R-cran-purrr \
		R-cran-rlang>=1.0.3:devel/R-cran-rlang \
		R-cran-tibble>0:devel/R-cran-tibble \
		R-cran-tidyr>=1.0.0:devel/R-cran-tidyr \
		R-cran-tidyselect>=1.1.2:devel/R-cran-tidyselect \
		R-cran-timeDate>0:finance/R-cran-timeDate \
		R-cran-vctrs>0:devel/R-cran-vctrs \
		R-cran-withr>0:devel/R-cran-withr
BUILD_DEPENDS=	${CRAN_DEPENDS}
RUN_DEPENDS=	${CRAN_DEPENDS}

USES=		cran:auto-plist

.include <bsd.port.mk>
