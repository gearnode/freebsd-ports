PORTNAME=	MediaWiki-API
PORTVERSION=	0.52
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	OOP MediaWiki engine client

LICENSE=	GPLv3

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-JSON>=0:converters/p5-JSON \
		p5-libwww>=0:www/p5-libwww
TEST_DEPENDS=	p5-JSON-Any>=0:converters/p5-JSON-Any

NO_ARCH=	yes
USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
