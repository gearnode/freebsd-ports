PORTNAME=	unigine-heaven
PORTVERSION=	4.0
PORTREVISION=	4
CATEGORIES=	benchmarks linux
MASTER_SITES=	https://assets.unigine.com/d/
PKGNAMEPREFIX=	linux-
DISTNAME=	Unigine_Heaven-${PORTVERSION}
EXTRACT_SUFX=	.run

MAINTAINER=	h2+fbsdports@fsfe.org
COMMENT=	Unigine Heaven benchmark (basic version for GNU/Linux)

LICENSE=	Proprietary
LICENSE_NAME=	Unigine "Basic" License
LICENSE_TEXT=	Binary only, License text not available. Free-to-use + no-redistribution implied from homepage
LICENSE_PERMS=	no-dist-sell no-pkg-sell no-dist-mirror no-pkg-mirror

ONLY_FOR_ARCHS=	amd64 i386
USES=		linux shebangfix
USE_LINUX=	dri openal-soft xorglibs
USE_LDCONFIG=	yes
NO_BUILD=	yes

SHEBANG_FILES=	heaven
bash_CMD=	${LINUXBASE}/bin/bash
SUB_FILES=	wrapper.sh

DESKTOP_ENTRIES="Unigine Heaven" "${COMMENT}" "${DATADIR}/data/launcher/icon.png" \
		"${PKGNAMEPREFIX}${PORTNAME}" "Game;" false

do-extract:
	@${MKDIR} ${WRKSRC}
	@${TAIL} -n 1097642 ${DISTDIR}/${DISTFILES} | ${TAR} xzf - -C ${WRKSRC}

do-install:
	${INSTALL_SCRIPT} ${WRKDIR}/wrapper.sh \
		${STAGEDIR}${PREFIX}/bin/${PKGNAMEPREFIX}${PORTNAME}
	cd ${WRKSRC} && ${COPYTREE_SHARE} ./data ${STAGEDIR}${DATADIR}
	cd ${WRKSRC} && ${COPYTREE_SHARE} ./bin ${STAGEDIR}${DATADIR}
	cd ${WRKSRC} && ${COPYTREE_SHARE} ./documentation ${STAGEDIR}${DATADIR}
	${INSTALL_SCRIPT} ${WRKSRC}/heaven ${STAGEDIR}${DATADIR}/heaven

.include <bsd.port.mk>
