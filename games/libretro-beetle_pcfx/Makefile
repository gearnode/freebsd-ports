PORTNAME=	libretro-beetle_pcfx
PORTVERSION=	0.20220307
CATEGORIES=	games

MAINTAINER=	dmenelkir@gmail.com
COMMENT=	Standalone port of Mednafen PCFX to libretro

LICENSE=	GPLv2

USES=		compiler:c++11-lib gmake
USE_LDCONFIG=	yes

USE_GITHUB=	yes
GH_ACCOUNT=	libretro
GH_PROJECT=	beetle-pcfx-libretro
GH_TAGNAME=	00abc26

PLIST_FILES=	lib/libretro/mednafen_pcfx_libretro.so

do-install:
	${MKDIR} ${STAGEDIR}/${PREFIX}/lib/libretro;
	${INSTALL_LIB} ${WRKSRC}/mednafen_pcfx_libretro.so ${STAGEDIR}/${PREFIX}/lib/libretro;

.include <bsd.port.mk>
