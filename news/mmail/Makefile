PORTNAME=	mmail
DISTVERSION=	0.52
CATEGORIES=	news
MASTER_SITES=	SF/multimail/MultiMail/${PORTVERSION}

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Offline BBS mail packet reader supporting QWK/OMEN/SOUP/OPX/BLUEWAVE

RUN_DEPENDS=	zip:archivers/zip

USES=		gmake ncurses
MAKE_ARGS=	OPTS="" LIBS="${LDFLAGS} -lncurses"

PLIST_FILES=	bin/mmail \
		man/man1/mmail.1.gz

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/mm ${STAGEDIR}${PREFIX}/bin/mmail
	${INSTALL_MAN} ${WRKSRC}/mm.1 ${STAGEDIR}${MANPREFIX}/man/man1/mmail.1

.include <bsd.port.mk>
