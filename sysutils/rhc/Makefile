PORTNAME=	rhc
PORTVERSION=	1.32.2
PORTREVISION=	2
CATEGORIES=	sysutils
MASTER_SITES=	RG

MAINTAINER=	dereckson@gmail.com
COMMENT=	Administration console client for RedHat OpenShift

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	minitar:archivers/rubygem-minitar-cli \
		commander:devel/rubygem-commander \
		rubygem-highline>=1.6.11:devel/rubygem-highline \
		rubygem-httpclient>=2.4:www/rubygem-httpclient \
		rubygem-net-scp>=1.1.2:security/rubygem-net-scp \
		rubygem-net-ssh>=2.0.11:security/rubygem-net-ssh \
		rubygem-net-ssh-multi>=1.2.0:security/rubygem-net-ssh-multi \
		rubygem-open4>0:devel/rubygem-open4

NO_ARCH=	yes
USE_RUBY=	yes
USES=		gem

PLIST_FILES=	bin/rhc

.include <bsd.port.mk>
