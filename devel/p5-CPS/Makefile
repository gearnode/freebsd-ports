PORTNAME=	CPS
PORTVERSION=	0.19
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:PEVANS
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Manage flow of control in Continuation-Passing Style

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Future>0:devel/p5-Future
TEST_DEPENDS=	p5-Test-Identity>0:devel/p5-Test-Identity \
		p5-Test-Pod>=1:devel/p5-Test-Pod \
		p5-Test-Refcount>0:devel/p5-Test-Refcount \
		p5-Test-Fatal>0:devel/p5-Test-Fatal

USES=		perl5
USE_PERL5=	modbuild

.include <bsd.port.mk>
