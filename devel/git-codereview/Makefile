PORTNAME=	git-codereview
PORTVERSION=	1.0.3
DISTVERSIONPREFIX=	v
PORTREVISION=	3
CATEGORIES=	devel

MAINTAINER=	swills@FreeBSD.org
COMMENT=	Command-line tool for working with Gerrit

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=		go

USE_GITHUB=	yes
GH_ACCOUNT=	golang
GH_PROJECT=	review

GO_PKGNAME=	golang.org/x/review
GO_TARGET=	./git-codereview

PLIST_FILES=	bin/git-codereview

.include <bsd.port.mk>
