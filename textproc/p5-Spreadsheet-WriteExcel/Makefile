PORTNAME=	Spreadsheet-WriteExcel
PORTVERSION=	2.40
PORTREVISION=	1
CATEGORIES=	textproc perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Write to a cross-platform Excel binary file

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Date-Calc>=0:devel/p5-Date-Calc \
		p5-Date-Manip>=0:devel/p5-Date-Manip \
		p5-OLE-Storage_Lite>=0:devel/p5-OLE-Storage_Lite \
		p5-Parse-RecDescent>=0:devel/p5-Parse-RecDescent

OPTIONS_DEFINE=	DOCS EXAMPLES

USES=		perl5 shebangfix dos2unix
USE_PERL5=	configure
DOS2UNIX_REGEX=	"*.p[lm]"

SHEBANG_FILES=	examples/*.pl

post-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}/images
	@${MKDIR} ${STAGEDIR}${DOCSDIR}/tpj_images
	${INSTALL_DATA} ${WRKSRC}/docs/*.html ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/docs/images/* ${STAGEDIR}${DOCSDIR}/images
	${INSTALL_DATA} ${WRKSRC}/docs/tpj_images/* ${STAGEDIR}${DOCSDIR}/tpj_images

	@${MKDIR} ${STAGEDIR}${EXAMPLESDIR}
	${INSTALL_DATA} ${WRKSRC}/examples/README \
		${WRKSRC}/examples/republic.png ${STAGEDIR}${EXAMPLESDIR}
	${INSTALL_SCRIPT} ${WRKSRC}/examples/*.pl ${STAGEDIR}${EXAMPLESDIR}
	${INSTALL_DATA} ${WRKSRC}/examples/*.txt ${STAGEDIR}${EXAMPLESDIR}

.include <bsd.port.mk>
