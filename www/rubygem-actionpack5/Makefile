PORTNAME=	actionpack
PORTVERSION=	5.1.7
CATEGORIES=	www rubygems
MASTER_SITES=	RG
PKGNAMESUFFIX=	5

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Action Controller and Action View of Rails MVC Framework

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/MIT-LICENSE

RUN_DEPENDS=	rubygem-actionview5>=${PORTVERSION}:devel/rubygem-actionview5 \
		rubygem-activesupport5>=${PORTVERSION}:devel/rubygem-activesupport5 \
		rubygem-rack>=2.0,3<3,3:www/rubygem-rack \
		rubygem-rack-test>=0.6.3:www/rubygem-rack-test \
		rubygem-rails-dom-testing-rails5>=2.0<3:textproc/rubygem-rails-dom-testing-rails5 \
		rubygem-rails-html-sanitizer>=1.0.2<2:textproc/rubygem-rails-html-sanitizer

USES=		gem
USE_RUBY=	yes

NO_ARCH=	yes

PORTSCOUT=	limit:^5\.1\.

.include <bsd.port.mk>
