PORTNAME=	lumina-mediaplayer
DISTVERSIONPREFIX=	v
DISTVERSION=	1.6.2
CATEGORIES=	deskutils

MAINTAINER=	lbartoletti@FreeBSD.org
COMMENT=	Streaming media player from the Lumina Desktop

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/../../../LICENSE

USES=		compiler:c++11-lang desktop-file-utils gl gstreamer qmake qt:5
USE_GL=		gl
USE_GSTREAMER=	gl
USE_QT=		buildtools_build core concurrent gui \
		multimedia network svg widgets x11extras
USE_GITHUB=	yes
GH_ACCOUNT=	lumina-desktop
GH_PROJECT=	lumina

OPTIONS_DEFINE=	NLS
OPTIONS_SUB=	yes

NLS_USE=	qt=linguist_build
NLS_QMAKE_ON=	CONFIG+=WITH_I18N

WRKSRC_SUBDIR=	src-qt5/desktop-utils/${PORTNAME}

.include <bsd.port.mk>
