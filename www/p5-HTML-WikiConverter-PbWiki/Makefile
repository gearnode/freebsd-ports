PORTNAME=	HTML-WikiConverter-PbWiki
PORTVERSION=	0.01
PORTREVISION=	1
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Convert HTML to PbWiki markup

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-HTML-WikiConverter>=0.54:www/p5-HTML-WikiConverter \
		p5-URI>=1.35:net/p5-URI

USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
