PORTNAME=	File-Attributes
PORTVERSION=	0.04
PORTREVISION=	2
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Manipulate file metadata in Perl

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-YAML>=0:textproc/p5-YAML \
		p5-Directory-Scratch>=0:devel/p5-Directory-Scratch \
		p5-Best>=0:devel/p5-Best \
		p5-YAML-Syck>0:textproc/p5-YAML-Syck

USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
