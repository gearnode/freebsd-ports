PORTNAME=	grub2-bhyve
DISTVERSIONPREFIX=	v
DISTVERSION=	0.40
PORTREVISION=	8
CATEGORIES=	sysutils

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Grub-emu loader for bhyve

LICENSE=	GPLv3

BUILD_DEPENDS=	${LOCALBASE}/bin/flex:textproc/flex \
		help2man:misc/help2man

ONLY_FOR_ARCHS=	amd64
SSP_UNSAFE=	yes
USE_GITHUB=	yes
GH_ACCOUNT=	grehan-freebsd
USES=		bison gmake
USE_GCC=	yes:build
PLIST_FILES=	sbin/grub-bhyve
MAKE_JOBS_UNSAFE=	yes
GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--with-platform=emu CPP="" LEX=${LOCALBASE}/bin/flex \
		--enable-grub-mount=no --enable-grub-mkfont=no \
		--enable-grub-emu-sdl=no --disable-nls --disable-werror

post-patch:
	@${REINPLACE_CMD} -e "s/libintl\.h/I_do_not_want_libintl.h/g" ${WRKSRC}/configure
	@${REINPLACE_CMD} -e "s/-lintl//g" ${WRKSRC}/grub-core/Makefile.in

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/grub-core/grub-emu ${STAGEDIR}${LOCALBASE}/sbin/grub-bhyve

.include <bsd.port.mk>
