PORTNAME=	privatebin-cli
DISTVERSIONPREFIX=	v
DISTVERSION=	1.1.1
CATEGORIES=	www security

MAINTAINER=	bryan@frimin.fr
COMMENT=	Simple portable command-line interface for privatebin server

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

USES=	go:modules

USE_GITHUB=	yes
GH_ACCOUNT=	gearnode
GH_PROJECT=	privatebin
GH_TUPLE=       gearnode:base58:69e2d70f0e30:gearnode_base58/vendor/github.com/gearnode/base58 \
		golang:crypto:530e935923ad:golang_crypto/vendor/golang.org/x/crypto

GO_TARGET=	./cmd/privatebin:privatebin

OPTIONS_DEFINE=	MANPAGES

OPTIONS_DEFAULT=	MANPAGES

MANPAGES_BUILD_DEPENDS= pandoc:textproc/hs-pandoc

do-build-MANPAGES-on:
	@cd ${WRKSRC} && ${MAKE} man

do-install-MANPAGES-on:
	${INSTALL_MAN} ${WRKSRC}/man/privatebin.1 ${STAGEDIR}${PREFIX}/man/man1
	${INSTALL_MAN} ${WRKSRC}/man/privatebin.conf.5 ${STAGEDIR}${PREFIX}/man/man5

.include <bsd.port.mk>
