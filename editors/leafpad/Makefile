PORTNAME=	leafpad
PORTVERSION=	0.8.18.1
PORTREVISION=	2
CATEGORIES=	editors
MASTER_SITES=	SAVANNAH

MAINTAINER=	jgh@FreeBSD.org
COMMENT=	GTK+ based simple text editor

LICENSE=	GPLv2

USE_GNOME=	gtk20 intlhack
USES=		desktop-file-utils gettext gmake gnome pkgconfig
GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--enable-chooser
CPPFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-lpthread -L${LOCALBASE}/lib

PORTDOCS=	AUTHORS COPYING ChangeLog INSTALL README

OPTIONS_DEFINE=	DOCS

post-extract:
	@${CHMOD} a+x ${WRKSRC}/install-sh

post-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${PORTDOCS:S,^,${WRKSRC}/,} ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
