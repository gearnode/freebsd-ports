PORTNAME=	lisaem
PORTVERSION=	1.2.6.2
PORTREVISION=	2
CATEGORIES=	emulators
MASTER_SITES=	http://lisaem.sunder.net/downloads/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Apple Lisa 2 Emulator

LICENSE=	GPLv2+
LICENSE_FILE=	${WRKSRC}/COPYING

BROKEN_FreeBSD_13=	ld: error: duplicate symbol: mem68k_fetch_byte
BROKEN_FreeBSD_14=	ld: error: duplicate symbol: mem68k_fetch_byte

BUILD_DEPENDS=	pngtopnm:graphics/netpbm

USES=		compiler:c++11-lang tar:bzip2
USE_WX=		2.8

BINARY_ALIAS=	wx-config=${WX_CONFIG}

CXXFLAGS+=	${CXXFLAGS_${CHOSEN_COMPILER_TYPE}}
CXXFLAGS_clang=	-Wno-c++11-narrowing

DESKTOP_ENTRIES="LisaEm" "" "lisaem" "lisaem" "" ""

post-patch:
	@${REINPLACE_CMD} -e \
		's|^inline |static inline |' ${WRKSRC}/lisa/zilog8530.c

do-build:
	${FIND} ${WRKSRC} -type l -delete
	cd ${WRKSRC} && ${SETENV} ${MAKE_ENV} ./build.sh build \
		--without-optimize
	${GREP} -v "^//" ${WRKSRC}/resources/lisa128x85.xpm | \
		${LOCALBASE}/bin/xpmtoppm | ${LOCALBASE}/bin/pnmtopng \
		>  ${WRKDIR}/lisaem.png

do-install:
	(cd ${WRKSRC}/bin && ${INSTALL_PROGRAM} * ${STAGEDIR}${PREFIX}/bin)
	(cd ${WRKDIR} && ${INSTALL_DATA} lisaem.png ${STAGEDIR}${PREFIX}/share/pixmaps)
	@${MKDIR} ${STAGEDIR}${DATADIR}
	(cd ${WRKSRC}/resources && ${INSTALL_DATA} * ${STAGEDIR}${DATADIR})
	${LN} -sf lisaem ${STAGEDIR}${PREFIX}/share/LisaEm

.include <bsd.port.mk>
