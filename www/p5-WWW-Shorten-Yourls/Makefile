PORTNAME=	WWW-Shorten-Yourls
PORTVERSION=	0.06
PORTREVISION=	1
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	beastie@tardisi.com
COMMENT=	Perl interface to www/yourls, Your Own URL Shortener

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-JSON-Any>=1.18:converters/p5-JSON-Any \
		p5-WWW-Shorten>=1.9:www/p5-WWW-Shorten \
		p5-XML-Simple>=2.18:textproc/p5-XML-Simple

USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
