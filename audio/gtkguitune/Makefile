PORTNAME=	gtkguitune
PORTVERSION=	0.8
DISTVERSIONPREFIX=	gtk2-
PORTREVISION=	12
CATEGORIES=	audio
MASTER_SITES=	GENTOO \
		http://www.oocities.org/harpin_floh/mysoft/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Guitar (and other instruments) tuner for GTK+2

LICENSE=	GPLv2+

WRKSRC=		${WRKDIR}/${PORTNAME}

USES=		compiler:c++11-lang gnome pkgconfig
USE_CXXSTD=	c++11
USE_GNOME=	gtkmm24
GNU_CONFIGURE=	yes

PLIST_FILES=	bin/${PORTNAME} \
		share/icons/hicolor/scalable/apps/guitune_logo.svg

DESKTOP_ENTRIES="GtkGuitune" "" "guitune_logo" "${PORTNAME}" "" ""

post-patch:
	@${REINPLACE_CMD} -e \
		's|VERSION=0.7|VERSION=${PORTVERSION}|g' ${WRKSRC}/configure
.for i in guitune.cc main.cc
	@${REINPLACE_CMD} -e \
		's|<linux/soundcard.h>|<sys/soundcard.h>|' ${WRKSRC}/${i}
.endfor

.include <bsd.port.mk>
