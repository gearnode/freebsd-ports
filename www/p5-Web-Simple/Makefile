PORTNAME=	Web-Simple
PORTVERSION=	0.033
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Quick and easy way to build simple web applications

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-HTTP-Body>=1.22:www/p5-HTTP-Body \
		p5-Moo>=0.009014:devel/p5-Moo \
		p5-Plack>=0.9968:www/p5-Plack \
		p5-Syntax-Keyword-Gather>=1.001000:devel/p5-Syntax-Keyword-Gather \
		p5-strictures>=1:devel/p5-strictures
TEST_DEPENDS=	p5-Data-Dumper-Concise>=2.20:devel/p5-Data-Dumper-Concise

USES=		perl5
USE_PERL5=	configure

NO_ARCH=	yes

.include <bsd.port.mk>
