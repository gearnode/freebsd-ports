PORTNAME=	Data-Object-State
PORTVERSION=	2.00
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Singleton Builder for Data::Object

LICENSE=	APACHE20

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Moo>=0:devel/p5-Moo \
		p5-routines>=0:devel/p5-routines
TEST_DEPENDS=	p5-Test-Auto>=0.10:devel/p5-Test-Auto

USES=		perl5
USE_PERL5=	configure

NO_ARCH=	yes

.include <bsd.port.mk>
