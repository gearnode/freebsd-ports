PORTNAME=	elfsh
PORTVERSION=	0.51b3
PORTREVISION=	5
CATEGORIES=	devel
MASTER_SITES=	http://elfsh.asgardlabs.org/files/
DISTNAME=	elfsh-0.51b3-portable

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Attractive toolkit for the analysis of ELF object files

USES=		gmake ncurses readline tar:tgz
USE_LDCONFIG=	yes

WRKSRC=		${WRKDIR}/${PORTNAME}-${PORTVERSION}

pre-install:
	@(cd ${WRKSRC} && \
		${STRIP_CMD} vm/elfsh libelfsh/libelfsh.so modules/*.so)

.include <bsd.port.mk>
