PORTNAME=	hipercontracer
PORTVERSION=	1.6.0
CATEGORIES=	benchmarks
MASTER_SITES=	https://www.uni-due.de/~be0001/hipercontracer/download/

MAINTAINER=	dreibh@iem.uni-due.de
COMMENT=	High-Performance Connectivity Tracer (HiPerConTracer)

LICENSE=	GPLv3+
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libboost_date_time.so:devel/boost-libs \
		libboost_filesystem.so:devel/boost-libs \
		libboost_iostreams.so:devel/boost-libs \
		libboost_log.so:devel/boost-libs \
		libboost_program_options.so:devel/boost-libs \
		libboost_system.so:devel/boost-libs \
		libboost_thread.so:devel/boost-libs

BROKEN=		error: expected '(' for function-style cast or type construction

USES=		cmake compiler:c++14-lang python shebangfix tar:xz
USE_LDCONFIG=	yes

SHEBANG_FILES=	src/addressinfogenerator src/get-default-ips src/tracedataimporter

CMAKE_ARGS+=	-DCMAKE_INSTALL_MANDIR=${PREFIX}/man
PLIST_SUB=	PORTVERSION=${PORTVERSION}

.include <bsd.port.mk>
