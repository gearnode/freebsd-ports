PORTNAME=	ghmm
DISTVERSION=	0.9-rc3
PORTREVISION=	2
CATEGORIES=	science math
MASTER_SITES=	SF/${PORTNAME}/${PORTNAME}/${PORTNAME}%20${DISTVERSION}

MAINTAINER=	ports@FreeBSD.org
COMMENT=	General Hidden Markov Model Library in C

LICENSE=	GPLv3

#BUILD_DEPENDS=	swig:devel/swig13

GNU_CONFIGURE=	yes
INSTALL_TARGET=	install-strip
USE_GNOME=	libxml2
USES=		autoreconf gnome libtool pkgconfig
CONFIGURE_ARGS+=	--without-python

USE_LDCONFIG=	yes

CONFLICTS_INSTALL=	graphviz # bin/cluster

.include <bsd.port.mk>
