PORTNAME=	libXi
DISTVERSION=	1.8
PORTEPOCH=	1
CATEGORIES=	x11

MAINTAINER=	x11@FreeBSD.org
COMMENT=	X Input extension library

LICENSE=	MIT

USES=		cpe xorg xorg-cat:lib
CPE_VENDOR=	x.org
USE_XORG=	x11 xext xfixes xorgproto

INSTALL_TARGET=	install-strip

CONFIGURE_ARGS+=--disable-docs \
		--disable-specs \
		--without-xmlto \
		--without-fop \
		--without-asciidoc \
		--without-xsltproc

.include <bsd.port.mk>
