PORTNAME=	VM-EC2
PORTVERSION=	1.28
PORTREVISION=	1
CATEGORIES=	net perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Perl interface to Amazon EC2 services

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-AnyEvent-CacheDNS>=0.08:dns/p5-AnyEvent-CacheDNS \
		p5-AnyEvent-HTTP>=2.15:www/p5-AnyEvent-HTTP \
		p5-AnyEvent>=7.04,1:devel/p5-AnyEvent \
		p5-JSON>=0:converters/p5-JSON \
		p5-String-Approx>=3.26:devel/p5-String-Approx \
		p5-URI>=1.40:net/p5-URI \
		p5-XML-Simple>=2.18:textproc/p5-XML-Simple \
		p5-libwww>=5.835:www/p5-libwww

USES=		perl5
USE_PERL5=	modbuild

NO_ARCH=	yes

.include <bsd.port.mk>
