PORTNAME=	qnapi
PORTVERSION=	0.2.3
PORTREVISION=	9
CATEGORIES=	polish multimedia

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Qt5 based subtitle downloader

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/doc/LICENSE

BUILD_DEPENDS=	qt-maybe>0:devel/qt-maybe \
		libmaia>0:net/libmaia
LIB_DEPENDS=	libmediainfo.so:multimedia/libmediainfo \
		libzen.so:multimedia/libzen
RUN_DEPENDS=	7zz:archivers/7-zip

USE_GITHUB=	yes

USES=		compiler:c++11-lib gl pkgconfig qmake qt:5
USE_GL=		gl
USE_QT=		buildtools_build core gui network widgets xml

CXXFLAGS+=	-I${LOCALBASE}/include/maia

post-patch:
	${REINPLACE_CMD} 's|/usr|${PREFIX}|' \
		${WRKSRC}/qnapi.pro
	${REINPLACE_CMD} 's,/usr/local,${LOCALBASE},' \
		${WRKSRC}/libqnapi/src/config/configreader.cpp

post-install:
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/qnapi
	(cd ${WRKSRC}/doc && ${INSTALL_DATA} qnapi-download.desktop \
		qnapi-scan.desktop ${STAGEDIR}${DESKTOPDIR})

.include <bsd.port.mk>
