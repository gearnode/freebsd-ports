PORTNAME=	devise
PORTVERSION=	4.8.1
CATEGORIES=	devel rubygems
MASTER_SITES=	RG
PKGNAMESUFFIX=	-rails52

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Flexible authentication solution for Rails with Warden

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/MIT-LICENSE

RUN_DEPENDS=	rubygem-bcrypt>=3.0<4:security/rubygem-bcrypt \
		rubygem-orm_adapter>=0.1<1:devel/rubygem-orm_adapter \
		rubygem-railties52>=4.1.0:www/rubygem-railties52 \
		rubygem-responders-rails52>=0:www/rubygem-responders-rails52 \
		rubygem-warden>=1.2.3<1.3:devel/rubygem-warden

USES=		cpe gem
USE_RUBY=	yes

NO_ARCH=	yes

CPE_VENDOR=	plataformatec

.include <bsd.port.mk>
