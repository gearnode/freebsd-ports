PORTNAME=	polyclipping
PORTVERSION=	6.4.2
CATEGORIES=	graphics
MASTER_SITES=	SF/${PORTNAME}
DISTNAME=	clipper_ver${PORTVERSION}

MAINTAINER=	sikmir@gmail.com
COMMENT=	Polygon and line clipping and offsetting library

LICENSE=	BSL
LICENSE_FILE=	${WRKSRC}/License.txt

USES=		cmake zip
USE_LDCONFIG=	yes

NO_WRKSUBDIR=	yes

CMAKE_SOURCE_PATH=	${WRKSRC}/cpp

PLIST_FILES=	include/polyclipping/clipper.hpp \
		lib/libpolyclipping.so \
		lib/libpolyclipping.so.22 \
		lib/libpolyclipping.so.22.0.0 \
		libdata/pkgconfig/polyclipping.pc

post-patch:
	@${REINPLACE_CMD} -e 's|share/pkgconfig|libdata/pkgconfig|' ${WRKSRC}/cpp/CMakeLists.txt

.include <bsd.port.mk>
