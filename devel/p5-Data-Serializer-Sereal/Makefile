PORTNAME=	Data-Serializer-Sereal
PORTVERSION=	1.05
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Creates bridge between Data::Serializer and Sereal

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Data-Serializer>=0:devel/p5-Data-Serializer \
		p5-Sereal-Decoder>=0:converters/p5-Sereal-Decoder \
		p5-Sereal-Encoder>=0:converters/p5-Sereal-Encoder

USES=		perl5
USE_PERL5=	configure
NO_ARCH=	yes

.include <bsd.port.mk>
