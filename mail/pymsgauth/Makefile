PORTNAME=	pymsgauth
PORTVERSION=	2.1.0
PORTREVISION=	2
CATEGORIES=	mail python
MASTER_SITES=	http://pyropus.ca/software/pymsgauth/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Automatically process qsecretary confirmation requests

LICENSE=	GPLv2 # only
LICENSE_FILE=	${WRKSRC}/COPYING

USES=		python shebangfix
SHEBANG_FILES=	pymsgauth-clean pymsgauth-confirm pymsgauth-mail \
		ConfParser.py pymsgauth.py
NO_BUILD=	yes
NO_ARCH=	yes

SUB_FILES=	pkg-message

PORTDOCS=	BUGS CHANGELOG pymsgauth.txt pymsgauth.html
PORTEXAMPLES=	pymsgauthrc-example

OPTIONS_DEFINE=	DOCS EXAMPLES

do-install:
	@${MKDIR} ${STAGEDIR}${DATADIR}
	${INSTALL_SCRIPT} ${WRKSRC}/*.py ${WRKSRC}/pymsgauth-* \
		${STAGEDIR}${DATADIR}
.for f in clean confirm mail
	${LN} -sf ${DATADIR}/pymsgauth-${f} ${STAGEDIR}${PREFIX}/bin
.endfor

do-install-EXAMPLES-on:
	@${MKDIR} ${STAGEDIR}${EXAMPLESDIR}
	${INSTALL_DATA} ${PORTEXAMPLES:S|^|${WRKSRC}/|} ${STAGEDIR}${EXAMPLESDIR}

do-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${PORTDOCS:S|^|${WRKSRC}/|} ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
