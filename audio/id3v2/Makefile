PORTNAME=	id3v2
PORTVERSION=	0.1.12
CATEGORIES=	audio
MASTER_SITES=	SF

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Command line id3v2 tag editor

LICENSE=	LGPL21

LIB_DEPENDS=	libid3.so:audio/id3lib

USES=		compiler:c++11-lang

MAKE_JOBS_UNSAFE=	yes

PLIST_FILES=	bin/id3v2 \
		share/man/man1/id3v2.1.gz

.include <bsd.port.mk>
