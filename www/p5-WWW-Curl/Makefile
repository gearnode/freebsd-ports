PORTNAME=	WWW-Curl
PORTVERSION=	4.17
PORTREVISION=	4
CATEGORIES=	www ftp perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Perl extension interface for libcurl

LICENSE=	MIT

LIB_DEPENDS=	libcurl.so:ftp/curl
TEST_DEPENDS=	p5-Test-CPAN-Meta>=0:devel/p5-Test-CPAN-Meta \
		p5-Test-Pod>=1.14:devel/p5-Test-Pod \
		p5-Test-Pod-Coverage>=1.04:devel/p5-Test-Pod-Coverage

USES=		perl5
USE_PERL5=	configure

post-install:
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/${SITE_ARCH_REL}/auto/WWW/Curl/Curl.so

.include <bsd.port.mk>
