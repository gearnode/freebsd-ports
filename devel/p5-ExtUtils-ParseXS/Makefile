PORTNAME=	ExtUtils-ParseXS
PORTVERSION=	3.35
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:SMUELLER
PKGNAMEPREFIX=	p5-

MAINTAINER=	demon@FreeBSD.org
COMMENT=	Converts Perl XS code into C code

LICENSE=	ART10

USES=		perl5 shebangfix
USE_PERL5=	configure
# Overwrite this here
perl_OLD_CMD=	perl
SHEBANG_FILES=	lib/ExtUtils/xsubpp

post-patch:
	@${REINPLACE_CMD} '/EXE_FILES/d' ${WRKSRC}/Makefile.PL

.include <bsd.port.mk>
