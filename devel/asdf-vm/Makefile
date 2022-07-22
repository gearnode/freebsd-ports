PORTNAME=	asdf-vm
DISTVERSIONPREFIX=	v
DISTVERSION=	0.10.2
CATEGORIES=	devel

MAINTAINER=	bryan@frimin.fr
COMMENT=	Extendable version manager

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	libyaml.so:textproc/libyaml \
		libreadline.so:devel/readline

RUN_DEPENDS=	bash:shells/bash \
		git:devel/git \
		curl:ftp/curl \
		unzip:archivers/unzip \
		autoconf:devel/autoconf \
		automake:devel/automake \
		gbase64:sysutils/coreutils \
		libtool:devel/libtool

USE_GITHUB=	yes
GH_ACCOUNT=	asdf-vm
GH_PROJECT=	asdf

NO_BUILD=	yes
NO_ARCH=	yes

do-install:
	${MKDIR} ${STAGEDIR}${DATADIR}

	${CP} -r ${WRKSRC}/bin ${STAGEDIR}${DATADIR}
	${CP} -r ${WRKSRC}/lib ${STAGEDIR}${DATADIR}
	${CP} ${WRKSRC}/asdf.elv ${STAGEDIR}${DATADIR}
	${CP} ${WRKSRC}/asdf.fish ${STAGEDIR}${DATADIR}
	${CP} ${WRKSRC}/asdf.sh ${STAGEDIR}${DATADIR}
	${CP} ${WRKSRC}/defaults ${STAGEDIR}${DATADIR}
	${CP} ${WRKSRC}/help.txt ${STAGEDIR}${DATADIR}
	${CP} ${WRKSRC}/version.txt ${STAGEDIR}${DATADIR}

	${MKDIR} ${STAGEDIR}${DOCSDIR}
	${CP} ${WRKSRC}/docs/[^_]*md ${STAGEDIR}${DOCSDIR}
	${CP} ${WRKSRC}/ballad-of-asdf.md \
		${STAGEDIR}${DOCSDIR}
	${CP} ${WRKSRC}/help.txt \
		${STAGEDIR}${DOCSDIR}
	${CP} ${WRKSRC}/CHANGELOG.md \
		${STAGEDIR}${DOCSDIR}
	${CP} ${WRKSRC}/CONTRIBUTING.md \
		${STAGEDIR}${DOCSDIR}
	${CP} ${WRKSRC}/README.md \
		${STAGEDIR}${DOCSDIR}
	${CP} ${WRKSRC}/SECURITY.md \
		${STAGEDIR}${DOCSDIR}

	${INSTALL_SCRIPT} ${WRKSRC}/completions/asdf.bash \
		${STAGEDIR}${PREFIX}/share/bash-completion/completions/asdf.bash

	${INSTALL_SCRIPT} ${WRKSRC}/completions/asdf.fish \
		${STAGEDIR}${PREFIX}/share/fish/vendor_completions.d/asdf.fish

	${INSTALL_SCRIPT} ${WRKSRC}/completions/_asdf \
		${STAGEDIR}${PREFIX}/share/zsh/site-functions/_asdf

.include <bsd.port.mk>
