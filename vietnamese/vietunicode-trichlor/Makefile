PORTNAME=	vietunicode-trichlor
PORTVERSION=	2004.04.30
PORTREVISION=	6
CATEGORIES=	vietnamese x11-fonts
MASTER_SITES=	SF/vietunicode/VietFonts-TriChlor/TrichlorSet%20v2004
DISTNAME=	VietFonts_TriChlor_ttf

MAINTAINER=	ports@FreeBSD.org
COMMENT=	100% Viet Unicode compatible

USES=		zip
DIST_SUBDIR=	VietUnicode
NO_WRKSUBDIR=	yes
NO_BUILD=	yes

TTF=		vuUHoai_bold.ttf vuUHoai_bolditalic.ttf vuUHoai_italic.ttf \
		vuAnhMinh.ttf vuAnhMinh_bold.ttf vuAnhMinh_bolditalic.ttf \
		vuAnhMinh_italic.ttf \
		vuHeoMay.ttf vuHeoMay_bold.ttf vuHeoMay_bolditalic.ttf \
		vuHeoMay_italic.ttf \
		vuHoangYen.ttf vuHoangYen_bold.ttf vuHoangYen_bolditalic.ttf \
		vuHoangYen_italic.ttf \
		vuMinhQuan.ttf vuMinhQuan_bold.ttf vuMinhQuan_bolditalic.ttf \
		vuMinhQuan_italic.ttf \
		vuPhuongThao.ttf vuPhuongThao_bold.ttf \
		vuPhuongThao_bolditalic.ttf vuPhuongThao_italic.ttf \
		vuThaHuong.ttf vuThaHuong_bold.ttf vuThaHuong_bolditalic.ttf \
		vuThaHuong_italic.ttf vuUHoai.ttf

do-install:
	@${MKDIR} ${STAGEDIR}${FONTSDIR}
	(cd ${WRKSRC} && ${INSTALL_DATA} ${TTF} ${STAGEDIR}${FONTSDIR})

.include "${.CURDIR}/../../chinese/ttfm/Makefile.ttf"
.include <bsd.port.mk>
