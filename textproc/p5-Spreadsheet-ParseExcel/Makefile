PORTNAME=	Spreadsheet-ParseExcel
PORTVERSION=	0.65
PORTREVISION=	2
PORTEPOCH=	1
CATEGORIES=	textproc perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Get information from Excel file

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Crypt-RC4>=0:security/p5-Crypt-RC4 \
		p5-Digest-Perl-MD5>=0:security/p5-Digest-Perl-MD5 \
		p5-OLE-Storage_Lite>=0.19:devel/p5-OLE-Storage_Lite

USES=		perl5 shebangfix
SHEBANG_FILES=	sample/parse.pl \
		sample/xls2csv.pl
USE_PERL5=	configure
NO_ARCH=	yes

OPTIONS_DEFINE=	EXAMPLES

PORTEXAMPLES=	*

post-install-EXAMPLES-on:
	@${MKDIR} ${STAGEDIR}${EXAMPLESDIR}/Excel
	${INSTALL_DATA} ${WRKSRC}/sample/README ${STAGEDIR}${EXAMPLESDIR}
	${INSTALL_SCRIPT} ${WRKSRC}/sample/*.pl ${STAGEDIR}${EXAMPLESDIR}
	${INSTALL_DATA} ${WRKSRC}/sample/Excel/* ${STAGEDIR}${EXAMPLESDIR}/Excel

.include <bsd.port.mk>
