PORTNAME=	openpgm
DISTVERSIONPREFIX=	release-
DISTVERSION=	5-2-122
PORTREVISION=	6
CATEGORIES=	net devel

PATCH_SITES=	https://github.com/${GH_ACCOUNT}/${GH_PROJECT}/commit/
PATCHFILES=	ee25ff3d13f2639b4c3a42125e79f77f921c3320.patch:-p3

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Implementation of the PGM reliable multicast protocol

LICENSE=	LGPL21+
LICENSE_FILE=	${WRKSRC}/COPYING

USE_GITHUB=	yes
GH_ACCOUNT=	steve-o

GNU_CONFIGURE=	yes
USES=		autoreconf compiler:c11 pathfix perl5 libtool python:build
USE_PERL5=	build
USE_LDCONFIG=	yes
WRKSRC_SUBDIR=	openpgm/pgm
INSTALL_TARGET=	install-strip

OPTIONS_DEFINE=	DOCS EXAMPLES
PORTDOCS=	draft-ietf-rmt-bb-pgmcc-03.txt rfc3208.txt
PORTEXAMPLES=	*

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${PORTDOCS:S,^,${WRKSRC}/../doc/,} ${STAGEDIR}${DOCSDIR}

post-install-EXAMPLES-on:
	@${MKDIR} ${STAGEDIR}${EXAMPLESDIR}
	(cd ${WRKSRC}/examples && ${COPYTREE_SHARE} . ${STAGEDIR}${EXAMPLESDIR})

.include <bsd.port.mk>
