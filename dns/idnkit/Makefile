PORTNAME=	idnkit
PORTVERSION=	1.0
PORTREVISION=	7
CATEGORIES=	dns
MASTER_SITES=	http://www.nic.ad.jp/ja/idn/idnkit/download/sources/
DISTNAME=	${PORTNAME}-${PORTVERSION}-src

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Library to handle internationalized domain names

LICENSE=	JPNIC
LICENSE_NAME=	Japan Network Information Center license
LICENSE_FILE=	${WRKSRC}/LICENSE.txt
LICENSE_PERMS=	dist-mirror dist-sell pkg-mirror pkg-sell auto-accept

USES=		iconv libtool
GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	${ICONV_CONFIGURE_BASE} \
		--enable-runidn \
		--enable-extra-ace

USE_LDCONFIG=	yes

OPTIONS_DEFINE=	DOCS

post-patch:
	@${FIND} ${WRKSRC} -name Makefile.in | ${XARGS} ${REINPLACE_CMD} -e \
		's|mode=link $$(LD)|mode=link $$(CC)|'

post-install:
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/lib/*.so

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}/ja
	(cd ${WRKSRC} && ${INSTALL_DATA} ChangeLog NEWS README \
		${STAGEDIR}${DOCSDIR})
	${INSTALL_DATA} ${WRKSRC}/README.ja ${STAGEDIR}${DOCSDIR}/ja

.include <bsd.port.mk>
