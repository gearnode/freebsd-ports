PORTNAME=	gnome-pomodoro
PORTVERSION=	0.21.1
CATEGORIES=	deskutils gnome

MAINTAINER=	tagattie@FreeBSD.org
COMMENT=	Time management utility for GNOME

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/COPYING

BUILD_DEPENDS=	appstream-util:devel/appstream-glib \
		valac:lang/vala
LIB_DEPENDS=	libcanberra.so:audio/libcanberra \
		libgom-1.0.so:databases/gom \
		libpeas-1.0.so:devel/libpeas

USES=		desktop-file-utils gettext-tools gmake gnome gstreamer libtool meson \
		pkgconfig sqlite

USE_GITHUB=	yes

USE_GNOME=	cairo glib20 gtk30 introspection

GLIB_SCHEMAS=	org.gnome.pomodoro.gschema.xml \
		org.gnome.pomodoro.plugins.actions.gschema.xml \
		org.gnome.pomodoro.plugins.gnome.gschema.xml \
		org.gnome.pomodoro.plugins.sounds.gschema.xml

PORTDOCS=	NEWS README.md

OPTIONS_DEFINE=	DOCS

post-install-DOCS-on:
	${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_MAN} ${PORTDOCS:S|^|${WRKSRC}/|} ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
