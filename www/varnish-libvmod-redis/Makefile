PORTNAME=	libvmod-redis
PORTVERSION=	20220118
CATEGORIES=	www
PKGNAMEPREFIX=	varnish-

MAINTAINER=	zi@FreeBSD.org
COMMENT=	Varnish Module (vmod) for redis

LICENSE=	BSD2CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	libev.so:devel/libev \
		libhiredis.so:databases/hiredis
BUILD_DEPENDS=	rst2man:textproc/py-docutils@${PY_FLAVOR}

USES=		autoreconf compiler:c11 gmake libtool pkgconfig \
		python:3.5+,build varnish:7
USE_LDCONFIG=	yes

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--disable-static --disable-tls
INSTALL_TARGET=	install-strip
DOCSDIR=	${PREFIX}/share/doc/vmod-redis
MAKE_JOBS_UNSAFE=	yes

CFLAGS+=	-I${WRKSRC}/src

USE_GITHUB=	yes
GH_ACCOUNT=	carlosabalde
GH_TAGNAME=	5e1c20e

OPTIONS_DEFINE=	DOCS

post-patch:
	${REINPLACE_CMD} 's|$${VARNISHAPI_DATAROOTDIR}|${LOCALBASE}/share|' \
		${WRKSRC}/Makefile.am

.include <bsd.port.mk>
