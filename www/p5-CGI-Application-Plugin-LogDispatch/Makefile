PORTNAME=	CGI-Application-Plugin-LogDispatch
PORTVERSION=	1.02
PORTREVISION=	1
CATEGORIES=	www perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	bofh@FreeBSD.org
COMMENT=	Plugin that adds Log::Dispatch support to CGI::Application

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-CGI-Application>=0:www/p5-CGI-Application \
		p5-Log-Dispatch>=0:devel/p5-Log-Dispatch \
		p5-UNIVERSAL-require>=0:devel/p5-UNIVERSAL-require

USES=		perl5
USE_PERL5=	modbuild

.include <bsd.port.mk>
