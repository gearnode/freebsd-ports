PORTNAME=	XML-Filter-DOMFilter-LibXML
PORTVERSION=	0.04
CATEGORIES=	textproc perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Perl SAX Filter allowing DOM processing of selected subtrees

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-XML-LibXML>=0:textproc/p5-XML-LibXML
TEST_DEPENDS=	p5-XML-SAX-Writer>=0:textproc/p5-XML-SAX-Writer

NO_ARCH=	yes
USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
