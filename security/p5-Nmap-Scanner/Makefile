PORTNAME=	Nmap-Scanner
PORTVERSION=	1.0
PORTREVISION=	5
CATEGORIES=	security perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Perform and manipulate nmap scans using perl

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	nmap:security/nmap \
		p5-Class-Generate>=0:devel/p5-Class-Generate \
		p5-XML-SAX>=0:textproc/p5-XML-SAX \
		p5-libwww>=0:www/p5-libwww

NO_ARCH=	yes
USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
