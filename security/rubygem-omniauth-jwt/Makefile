PORTNAME=	omniauth-jwt
PORTVERSION=	0.0.2
PORTREVISION=	1
CATEGORIES=	security rubygems
MASTER_SITES=	RG

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	OmniAuth strategy to accept JWT-based single sign-on

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

RUN_DEPENDS=	rubygem-jwt>=0:www/rubygem-jwt \
		rubygem-omniauth1>=1.1<2:security/rubygem-omniauth1

USES=		gem
USE_RUBY=	yes

NO_ARCH=	yes

.include <bsd.port.mk>
