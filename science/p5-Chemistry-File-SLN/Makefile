PORTNAME=	Chemistry-File-SLN
PORTVERSION=	0.11
PORTREVISION=	1
CATEGORIES=	science perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:ITUB
PKGNAMEPREFIX=	p5-

MAINTAINER=	swills@FreeBSD.org
COMMENT=	SLN linear notation parser/writer

BUILD_DEPENDS=	p5-Chemistry-Mol>=0:science/p5-Chemistry-Mol \
		p5-Chemistry-Ring>=0:science/p5-Chemistry-Ring \
		p5-Chemistry-Canonicalize>=0:science/p5-Chemistry-Canonicalize \
		p5-Chemistry-Bond-Find>=0:science/p5-Chemistry-Bond-Find \
		p5-Parse-Yapp>=0:devel/p5-Parse-Yapp
RUN_DEPENDS=	p5-Chemistry-Mol>=0:science/p5-Chemistry-Mol \
		p5-Chemistry-Ring>=0:science/p5-Chemistry-Ring \
		p5-Chemistry-Canonicalize>=0:science/p5-Chemistry-Canonicalize \
		p5-Chemistry-Bond-Find>=0:science/p5-Chemistry-Bond-Find \
		p5-Parse-Yapp>=0:devel/p5-Parse-Yapp

USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
