PORTNAME=	poly1305aes
PORTVERSION=	20050218
CATEGORIES=	security
MASTER_SITES=	http://cr.yp.to/mac/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Poly1305 message authentication reference implementation using AES

LICENSE=	PD

BROKEN_aarch64=		fails to build: poly1305aes.impl.do: fatal: all tests failed
BROKEN_armv6=		fails to build: poly1305aes.impl.do: fatal: all tests failed
BROKEN_armv7=		fails to build: poly1305aes.impl.do: fatal: all tests failed
BROKEN_riscv64=		fails to build: poly1305aes.impl.do: fatal: all tests failed
NOT_FOR_ARCHS=	amd64

ALL_TARGET=	default

CC+=		${CPPFLAGS} ${CFLAGS} ${LDFLAGS}

.include <bsd.port.pre.mk>

.if ${ARCH:Mpowerpc*}
USE_GCC=	yes
.elif ${ARCH} == "i386"
pre-build:
	@${ECHO_CMD} "ppro" > ${WRKSRC}/poly1305aes.impl
.endif

post-build:
.for i in aes.h cpucycles.h poly1305aes.h
	@${REINPLACE_CMD} -e \
		's|#include "|#include "poly1305/|' ${WRKSRC}/${i}
.endfor

do-install:
.for i in poly1305aes-speed test-aes test-poly1305aes
	(cd ${WRKSRC} && ${INSTALL_PROGRAM} ${i} \
		${STAGEDIR}${PREFIX}/bin)
.endfor
	@${MKDIR} ${STAGEDIR}${PREFIX}/include/poly1305
	(cd ${WRKSRC} && ${INSTALL_DATA} *.h \
		${STAGEDIR}${PREFIX}/include/poly1305)
	(cd ${WRKSRC} && ${INSTALL_DATA} *.a \
		${STAGEDIR}${PREFIX}/lib)

.include <bsd.port.post.mk>
