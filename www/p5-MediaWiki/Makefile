PORTNAME=	MediaWiki
PORTVERSION=	1.13
PORTREVISION=	1
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:SPECTRUM
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	OOP MediaWiki engine client

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Config-IniHash>=0:devel/p5-Config-IniHash \
		p5-libwww>=0:www/p5-libwww

USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
