PORTNAME=	DocSet
PORTVERSION=	0.19
PORTREVISION=	3
CATEGORIES=	textproc www perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:STAS
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Documentation projects builder in HTML, PS, and PDF formats

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Pod-POM>=0:textproc/p5-Pod-POM \
		p5-Template-Toolkit>=0:www/p5-Template-Toolkit

USES=		perl5
USE_PERL5=	configure

CONFLICTS_INSTALL=	html2ps # bin/html2ps

.include <bsd.port.mk>
