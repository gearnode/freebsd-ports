PORTNAME=	Excel-Writer-XLSX
PORTVERSION=	1.09
CATEGORIES=	textproc perl5
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:JMCNAMARA
PKGNAMEPREFIX=	p5-

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Create a new file in the Excel 2007+ XLSX format

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual
LICENSE_FILE_ART10=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Archive-Zip>=1.30:archivers/p5-Archive-Zip
TEST_DEPENDS=	p5-Date-Calc>=0:devel/p5-Date-Calc \
		p5-Date-Manip>=0:devel/p5-Date-Manip

USES=		perl5
USE_PERL5=	configure

NO_ARCH=	yes

.include <bsd.port.mk>
