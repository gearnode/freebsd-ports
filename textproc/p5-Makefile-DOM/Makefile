PORTNAME=	Makefile-DOM
PORTVERSION=	0.008
PORTREVISION=	1
CATEGORIES=	textproc perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:AGENT
PKGNAMEPREFIX=	p5-

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Simple DOM parser for Makefiles

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Clone>=0.18:devel/p5-Clone \
		p5-List-MoreUtils>=0.21:lang/p5-List-MoreUtils \
		p5-Params-Util>=0.22:devel/p5-Params-Util

USES=		perl5
USE_PERL5=	configure

NO_ARCH=	yes

.include <bsd.port.mk>
