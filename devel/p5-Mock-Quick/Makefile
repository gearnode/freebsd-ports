PORTNAME=	Mock-Quick
PORTVERSION=	1.111
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:EXODIST
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Quickly mock objects and classes

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Exporter-Declare>=0.103:devel/p5-Exporter-Declare
TEST_DEPENDS=	p5-Fennec-Lite>=0.004:devel/p5-Fennec-Lite \
		p5-Test-Exception>=0.29:devel/p5-Test-Exception

NO_ARCH=	yes
USES=		perl5
USE_PERL5=	modbuild

.include <bsd.port.mk>
