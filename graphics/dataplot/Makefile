PORTNAME=	dataplot
DISTVERSION=	20200619
CATEGORIES=	graphics

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Free software system for statistical visualization

LICENSE=	PD

LIB_DEPENDS=	libgd.so:graphics/gd \
		libpng.so:graphics/png

USES=		gmake gnome fortran jpeg readline xorg
USE_XORG=	x11 xi
USE_GNOME=	cairo

USE_GITHUB=	yes
GH_ACCOUNT=	usnistgov
GH_TAGNAME=	2c1b27601a3b7523449de612613eadeead9a8f70

WRKSRC_SUBDIR=	src

MAXOBV?=	450000	# Change if you need more observations/variable

FFLAGS+=	-DLINUX -fdefault-real-8 -fdefault-double-8 -std=legacy

PORTDATA=	*

PLIST_FILES=	bin/dataplot bin/xdataplot

OPTIONS_DEFINE=	DOCS

post-patch:
	@${REINPLACE_CMD} -e 's/MAXOBV=1500000/MAXOBV=${MAXOBV}/' \
		${WRKSRC}/DPCOPA.INC
	@${REINPLACE_CMD} \
		-e 's;%%FC%%;${FC};' \
		-e 's;%%CC%%;${CC};' \
		-e 's;%%FFLAGS%%;${FFLAGS};' \
		-e 's;%%CFLAGS%%;${CFLAGS};' \
		-e 's;%%DATADIR%%;${DATADIR};' \
		-e 's;%%LOCALBASE%%;${LOCALBASE};g' ${WRKSRC}/Makefile

post-build:
	@${STRIP_CMD} ${WRKSRC}/dataplot

.include <bsd.port.mk>
