PORTNAME=	Hash-AutoHash
PORTVERSION=	1.17
PORTREVISION=	1
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Object-oriented access to real and tied hashes

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-List-MoreUtils>=0.33:lang/p5-List-MoreUtils \
		p5-Tie-ToObject>=0.03:devel/p5-Tie-ToObject
TEST_DEPENDS=	p5-Test-Deep>=0.11:devel/p5-Test-Deep \
		p5-Tie-Hash-MultiValue>=1.02:devel/p5-Tie-Hash-MultiValue

USES=		perl5
USE_PERL5=	modbuild

NO_ARCH=	yes

.include <bsd.port.mk>
