PORTNAME=	MooseX-Daemonize
PORTVERSION=	0.22
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Role for daemonizing your Moose based application

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS} \
		p5-Devel-CheckOS>=1.63:devel/p5-Devel-CheckOS
RUN_DEPENDS=	p5-Moose>=0.33:devel/p5-Moose \
		p5-MooseX-Getopt>=0.07:devel/p5-MooseX-Getopt \
		p5-MooseX-Types-Path-Class>=0:devel/p5-MooseX-Types-Path-Class
TEST_DEPENDS=	p5-Test-Fatal>=0:devel/p5-Test-Fatal

NO_ARCH=	yes
USES=		perl5
USE_PERL5=	modbuildtiny

.include <bsd.port.mk>
