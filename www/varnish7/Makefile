PORTNAME=	varnish
DISTVERSION=	7.1.0
DISTVERSIONPREFIX=	varnish-
CATEGORIES=	www
PKGNAMESUFFIX=	7

MAINTAINER=	dbaio@FreeBSD.org
COMMENT=	High-performance HTTP accelerator

LICENSE=	BSD2CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	rst2man:textproc/py-docutils@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}sphinx>=0,1:textproc/py-sphinx@${PY_FLAVOR}
LIB_DEPENDS=	libpcre2-8.so:devel/pcre2

USES=		autoreconf compiler cpe gmake libedit libtool ncurses pathfix \
		pkgconfig python:3.6+,build readline shebangfix

CONFLICTS=	varnish4 varnish6

SHEBANG_FILES=	lib/libvcc/*.py lib/libvsc/*.py
CPE_VENDOR=	varnish-cache
CPE_PRODUCT=	varnish_cache
CFLAGS+=	-I${LOCALBASE}/include
GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--localstatedir=${PREFIX} --without-dot
USE_LDCONFIG=	yes
INSTALL_TARGET=	install-strip
TEST_TARGET=	check
TEST_ARGS=	TESTS_PARALLELISM=1

USE_GITHUB=	yes
GH_ACCOUNT=	varnishcache
GH_PROJECT=	varnish-cache

USERS=		varnish varnishlog
GROUPS=		varnish

USE_RC_SUBR=	varnishd varnishlog varnishncsa
.if defined(NO_INET6) || defined(WITHOUT_INET6)
BAD_TESTS+=	r00832
EXTRA_PATCHES+=	${FILESDIR}/no-inet6.patch
.endif

OPTIONS_DEFINE=	DOCS

.include <bsd.port.pre.mk>

post-patch:
.if defined(BAD_TESTS)
	${RM} ${BAD_TESTS:C|.+|${WRKSRC}/bin/varnishtest/tests/\0.vtc|}
.endif
.if ${CHOSEN_COMPILER_TYPE} == gcc
	${REINPLACE_CMD} -e '/-Wno-unknown-warning-option -Wno-implicit-fallthrough/d' ${WRKSRC}/configure.ac
.endif

.include <bsd.port.post.mk>
