PORTNAME=	railties
PORTVERSION=	5.0.7.2
CATEGORIES=	www rubygems
MASTER_SITES=	RG
PKGNAMESUFFIX=	50

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Rails internals bootup, plugins, generators, and rake tasks

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/MIT-LICENSE

RUN_DEPENDS=	rubygem-actionpack50>=${PORTVERSION}:www/rubygem-actionpack50 \
		rubygem-activesupport50>=${PORTVERSION}:devel/rubygem-activesupport50 \
		rubygem-method_source>=0:devel/rubygem-method_source \
		rubygem-rake>=0.8.7:devel/rubygem-rake \
		rubygem-thor>=0.18.1<2.0:devel/rubygem-thor

USES=		gem
USE_RUBY=	yes

NO_ARCH=	yes

PLIST_FILES=	bin/rails

CONFLICTS_INSTALL=	rubygem-railties4 rubygem-railties5 rubygem-railties52

PORTSCOUT=	limit:^5\.0\.

.include <bsd.port.mk>
