PORTNAME=	Geo-Coder-Bing
PORTVERSION=	0.13
CATEGORIES=	misc geography perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Geocode addresses with the Bing Maps API

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-JSON>=2:converters/p5-JSON \
		p5-JSON-XS>=2:converters/p5-JSON-XS \
		p5-LWP-Protocol-https>=6.02:www/p5-LWP-Protocol-https \
		p5-URI>=1.36:net/p5-URI \
		p5-libwww>=6.02:www/p5-libwww

USES=		perl5
USE_PERL5=	configure

NO_ARCH=	yes

.include <bsd.port.mk>
