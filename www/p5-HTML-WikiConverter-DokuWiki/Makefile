PORTNAME=	HTML-WikiConverter-DokuWiki
PORTVERSION=	0.53
PORTREVISION=	1
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Convert HTML to DokuWiki markup

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-HTML-WikiConverter>=0.60:www/p5-HTML-WikiConverter \
		p5-URI>=1.35:net/p5-URI

USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
