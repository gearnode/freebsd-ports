PORTNAME=	hevea
PORTVERSION=	2.34
CATEGORIES=	textproc
MASTER_SITES=	http://para.inria.fr/~maranget/hevea/distri/ \
		ftp://ftp.inria.fr/INRIA/moscova/hevea/
DISTFILES=	${DISTNAME}${EXTRACT_SUFX}
EXTRACT_ONLY=	${DISTNAME}${EXTRACT_SUFX}

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Convert LaTeX to HTML

BUILD_DEPENDS=	ocamlbuild:devel/ocaml-ocamlbuild

OPTIONS_DEFINE=	DOCS

PLIST_SUB=	HEVEAVERSION=${PORTVERSION}

PORTDOCS=	*
DOCS_DISTFILES+=	${PORTNAME}-${PORTVERSION}-manual.pdf \
			${PORTNAME}-${PORTVERSION}-manual.tar.gz

post-install:
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/esponja
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/bibhva
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/hevea
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/hacha

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${PREFIX}/share/doc/hevea
	${INSTALL_DATA} ${DISTDIR}/${PORTNAME}-${PORTVERSION}-manual.pdf ${STAGEDIR}${PREFIX}/share/doc/hevea
	(cd ${STAGEDIR}${PREFIX}/share/doc/hevea; ${TAR} xvfz ${DISTDIR}/${PORTNAME}-${PORTVERSION}-manual.tar.gz)

.include <bsd.port.mk>
