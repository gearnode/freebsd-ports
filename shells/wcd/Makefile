PORTNAME=	wcd
PORTVERSION=	6.0.3
CATEGORIES=	shells
MASTER_SITES=	SF

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Command-line program to change directory fast

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/doc/copying.txt

USES=		gmake ncurses
MAKE_ARGS=	EXT= PREFIX=${PREFIX} docsubdir=${PORTNAME} \
		mandir=${PREFIX}/man LIB_CURSES=-l${NCURSES_IMPL}
CFLAGS+=	-I${NCURSESINC}

OPTIONS_DEFINE=	DOCS NLS
OPTIONS_SUB=	yes

NLS_USES=	gettext
NLS_MAKE_ARGS_OFF=	ENABLE_NLS=

post-patch:
	@${REINPLACE_CMD} -e '/manfile/ s|datarootdir|prefix|' \
		-e 's|/usr/local|${LOCALBASE}|' \
		${WRKSRC}/src/Makefile

post-install:
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/wcd

.include <bsd.port.mk>
