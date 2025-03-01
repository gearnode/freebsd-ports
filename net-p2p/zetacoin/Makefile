PORTNAME=	zetacoin
PORTVERSION=	0.13.2.1
DISTVERSIONPREFIX=	v
PORTREVISION=	8
CATEGORIES=	net-p2p finance

MAINTAINER=	daniel@morante.net
COMMENT=	Peer-to-Peer crypto currency with quick transactions

LICENSE=	MIT

LIB_DEPENDS=	libboost_date_time.so:devel/boost-libs \
		libevent.so:devel/libevent

BROKEN=		error: use of undeclared identifier '_1'

USES=		autoreconf compiler:c++11-lib gmake libtool pkgconfig shebangfix ssl

USE_GITHUB=	yes

GNU_CONFIGURE=	yes

SLAVE_PORT?=	no

.if defined(SLAVE_PORT) && ${SLAVE_PORT} == "no"
USES+=		desktop-file-utils qt:5
USE_QT=		core gui network widgets \
		buildtools_build linguisttools_build qmake_build

BUILD_DEPENDS+=	protoc:devel/protobuf
LIB_DEPENDS+=	libprotobuf.so:devel/protobuf

TESTS_USES=	qt:5
TESTS_USE=		QT=testlib
TESTS_PLIST_FILES=	bin/test_${PORTNAME}-qt \
			bin/test_${PORTNAME}
.endif

OPTIONS_DEFINE?=	DBUS DEBUG HARDENING QRCODES TESTS UPNP WALLET_BDBMODERN ZMQ
OPTIONS_DEFAULT?=	DBUS HARDENING QRCODES UPNP WALLET_BDBMODERN ZMQ
OPTIONS_SUB=		yes

HARDENING_DESC=	Attempt to harden binaries (PIE for ASLR, NX Stack)
QRCODES_DESC=	Display QR Codes
TESTS_DESC=	Build test binary and unit tests
WALLET_BDBMODERN_DESC=	Wallet using modern BDB 5.x or 6.x
ZMQ_DESC=	Block and transaction broadcasting with ZeroMQ

DBUS_CONFIGURE_WITH=	dbus
DBUS_USES=	qt:5
DBUS_USE=		QT=dbus

DEBUG_CONFIGURE_ENABLE=		debug
DEBUG_INSTALL_TARGET_OFF=	install-strip

HARDENING_CONFIGURE_ENABLE=	hardening

TESTS_CONFIGURE_ENABLE=	tests bench
.if defined(SLAVE_PORT) && ${SLAVE_PORT} == "yes"
TESTS_PLIST_FILES=	bin/test_${PORTNAME}
.endif
TESTS_PLIST_FILES+=	bin/bench_${PORTNAME}

UPNP_CONFIGURE_WITH=	miniupnpc
UPNP_LIB_DEPENDS=	libminiupnpc.so:net/miniupnpc
UPNP_CPPFLAGS=		-I${LOCALBASE}/include
UPNP_LIBS=		-L${LOCALBASE}/lib

QRCODES_CONFIGURE_WITH=	qrencode
QRCODES_LIB_DEPENDS=	libqrencode.so:graphics/libqrencode

ZMQ_CONFIGURE_ENABLE=	zmq
ZMQ_BUILD_DEPENDS=	libzmq4>0:net/libzmq4
ZMQ_RUN_DEPENDS=	libzmq4>0:net/libzmq4

CONFIGURE_ARGS?=	--without-libs \
			--with-gui=qt5 \
			--without-daemon \
			--without-utils

CONFIGURE_ENV=	CRYPTO_CFLAGS="-I${OPENSSLINC}" CRYPTO_LIBS="-L${OPENSSLLIB} -lcrypto" \
		SSL_CFLAGS="-I${OPENSSLINC}" SSL_LIBS="-L${OPENSSLLIB} -lssl" \
		OBJCXX="${CXX}" OBJCXXFLAGS="${CXXFLAGS}"
MAKE_ENV+=	V=1

PLIST_FILES?=	bin/${PORTNAME}-qt share/applications/${PORTNAME}-qt.desktop \
		share/pixmaps/${PORTNAME}256.png

.include <bsd.port.options.mk>

.if ${PORT_OPTIONS:MWALLET_BDBMODERN}
CONFIGURE_ARGS+=	--enable-wallet --with-incompatible-bdb
USES+=			bdb:5+
.else
CONFIGURE_ARGS+=	--disable-wallet
.endif

.include <bsd.port.pre.mk>

.if ${PORT_OPTIONS:MWALLET_BDBMODERN}
CPPFLAGS+=	-I${BDB_INCLUDE_DIR}
LIBS+=		-L${BDB_LIB_DIR}
.endif

.if defined(SLAVE_PORT) && ${SLAVE_PORT} == "no"

post-install:
	${INSTALL} ${FILESDIR}/${PORTNAME}-qt.desktop \
		${STAGEDIR}${PREFIX}/share/applications
	${INSTALL} ${WRKSRC}/src/qt/res/icons/bitcoin.png \
		${STAGEDIR}${PREFIX}/share/pixmaps/${PORTNAME}256.png

.endif

regression-test: build
	# To use this sucessfully, remove --without-daemon and --without-utils
	# from CONFIGURE_ARGS above.

	@cd ${WRKSRC} && ${GMAKE} check

.include <bsd.port.post.mk>
