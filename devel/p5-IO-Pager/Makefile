PORTNAME=	IO-Pager
PORTVERSION=	2.10
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Select a pager, optionally pipe it output if destination is a TTY

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-File-Which>=0:sysutils/p5-File-Which \
		p5-Term-ReadKey>=0:devel/p5-Term-ReadKey

USES=		perl5 tar:tgz
USE_PERL5=	configure

NO_ARCH=	yes

.include <bsd.port.mk>
