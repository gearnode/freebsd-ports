PORTNAME=	WWW-SourceForge
PORTVERSION=	0.70
PORTREVISION=	3
PORTEPOCH=	1
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:RBOW
PKGNAMEPREFIX=	p5-

MAINTAINER=	ychsiao@ychsiao.org
COMMENT=	Retrieve information from SourceForge site

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-WWW-Mechanize>=0:www/p5-WWW-Mechanize \
		p5-HTML-TableExtract>=0:www/p5-HTML-TableExtract \
		p5-YAML>=0:textproc/p5-YAML

USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
