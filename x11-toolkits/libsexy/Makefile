PORTNAME=	libsexy
PORTVERSION=	0.1.11
PORTREVISION=	12
CATEGORIES=	x11-toolkits devel
MASTER_SITES=	http://releases.chipx86.com/libsexy/libsexy/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Extension widgets for GTK+

LICENSE=	LGPL21

LIB_DEPENDS=	libenchant.so:textproc/enchant
BUILD_DEPENDS=	${LOCALBASE}/libdata/pkgconfig/iso-codes.pc:misc/iso-codes
RUN_DEPENDS:=	${BUILD_DEPENDS}

GNU_CONFIGURE=	yes
USES=		gettext gnome libtool pathfix pkgconfig
USE_GNOME=	gtk20 libxml2
USE_LDCONFIG=	yes

post-patch:
	@${REINPLACE_CMD} -e 's|g_strncasecmp|g_ascii_strncasecmp|' \
		${WRKSRC}/libsexy/sexy-spell-entry.c

.include <bsd.port.mk>
