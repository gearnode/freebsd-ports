PORTNAME=	visualization.fishbmc
PORTVERSION=	19.0.1
DISTVERSIONSUFFIX=	-Matrix
CATEGORIES=	multimedia

MAINTAINER=	rozhuk.im@gmail.com
COMMENT=	Fische visualizer for Kodi

LICENSE=	GPLv2+

BUILD_DEPENDS=	glm>0:math/glm

USES=		cmake localbase compiler:c++14-lang gl kodi
USE_CXXSTD=	c++14
USE_GITHUB=	yes
GH_ACCOUNT=	xbmc
USE_GL=		egl gl glu

PLIST_SUB=	SOVERSION=${PORTVERSION}

CMAKE_ARGS=	-DADDONS_TO_BUILD=${PORTNAME}

.include <bsd.port.mk>
