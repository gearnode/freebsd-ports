PORTNAME=	WWW-GitHub-Gist
PORTVERSION=	0.17
PORTREVISION=	1
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Perl interface to Gist

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-JSON>=0:converters/p5-JSON \
		p5-Moo>=0:devel/p5-Moo

USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
