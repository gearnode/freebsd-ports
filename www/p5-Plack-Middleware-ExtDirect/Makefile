PORTNAME=	Plack-Middleware-ExtDirect
PORTVERSION=	3.20
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:TOKAREV
PKGNAMEPREFIX=	p5-

MAINTAINER=	martin@waschbuesch.de
COMMENT=	Implement an RPC::ExtDirect gateway using Plack

LICENSE=	ART10

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Plack>=0:www/p5-Plack \
		p5-RPC-ExtDirect>=3.20:www/p5-RPC-ExtDirect
TEST_DEPENDS=	p5-Test-Pod>=1.46:devel/p5-Test-Pod

USES=		perl5 pkgconfig:both
USE_PERL5=	configure
NO_ARCH=	YES

.include <bsd.port.mk>
