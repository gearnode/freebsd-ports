PORTNAME=	File-Flat
PORTVERSION=	1.07
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Implements a flat filesystem

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-File-Copy-Recursive>=0.35:devel/p5-File-Copy-Recursive \
		p5-File-Remove>=0.38:devel/p5-File-Remove \
		p5-prefork>=0.02:devel/p5-prefork
TEST_DEPENDS=	p5-Test-ClassAPI>=1.04:devel/p5-Test-ClassAPI

USES=		perl5
USE_PERL5=	configure

NO_ARCH=	yes

.include <bsd.port.mk>
