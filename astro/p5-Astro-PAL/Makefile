PORTNAME=	Astro-PAL
PORTVERSION=	1.09
CATEGORIES=	astro perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Perl interface to Starlink PAL positional astronomy library

LICENSE=	GPLv3

TEST_DEPENDS=	p5-Test-Number-Delta>=1:devel/p5-Test-Number-Delta

USES=		perl5
USE_PERL5=	modbuild

post-install:
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/${SITE_ARCH_REL}/auto/Astro/PAL/PAL.so

.include <bsd.port.mk>
