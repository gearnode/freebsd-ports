PORTNAME=	template_
PORTVERSION=	2.2.3
CATEGORIES=	www
MASTER_SITES=	http://www.xtac.net/download/?file=
DISTNAME=	Template_.2.2.3

MAINTAINER=	ports@FreeBSD.org
COMMENT=	High performance PHP compiling template engine

LICENSE=	LGPL20+

FETCH_ARGS+=	-o ${DISTNAME}.tar.gz

USES=		php:web
NO_WRKSUBDIR=	yes
NO_BUILD=	yes

do-install:
	@${MKDIR} ${STAGEDIR}${DATADIR}/tpl_plugin
.for f in Template_.class.php Template_.compiler.php
	${INSTALL_DATA} ${WRKSRC}/$f ${STAGEDIR}${DATADIR}
	${INSTALL_DATA} ${WRKSRC}/tpl_plugin/* ${STAGEDIR}${DATADIR}/tpl_plugin
.endfor

.include <bsd.port.mk>
