PORTNAME=	tty-pager
PORTVERSION=	0.14.0
CATEGORIES=	devel rubygems
MASTER_SITES=	RG

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Terminal output paging in cross-platform way

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

RUN_DEPENDS=	rubygem-strings>=0.2.0<0.3:devel/rubygem-strings \
		rubygem-tty-screen>=0.8<1:devel/rubygem-tty-screen

USES=		gem
USE_RUBY=	yes

NO_ARCH=	yes

.include <bsd.port.mk>
