PORTNAME=	tumblr_client
PORTVERSION=	0.8.5
PORTREVISION=	4
CATEGORIES=	www rubygems
MASTER_SITES=	RG

MAINTAINER=	ruby@FreeBSD.org
COMMENT=	Ruby Wrapper for the Tumblr v2 API

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	rubygem-faraday0>=0.9.0<1:www/rubygem-faraday0 \
		rubygem-faraday_middleware0>=0.9.0<1:www/rubygem-faraday_middleware0 \
		rubygem-json>=0:devel/rubygem-json \
		rubygem-mime-types>=0:misc/rubygem-mime-types \
		rubygem-oauth>=0:net/rubygem-oauth \
		rubygem-simple_oauth>=0:net/rubygem-simple_oauth

USES=		gem
USE_RUBY=	yes

NO_ARCH=	yes

PLIST_FILES=	bin/tumblr

.include <bsd.port.mk>
