PORTNAME=	postgresql
PORTREVISION=	0
CATEGORIES=	databases

MAINTAINER=	pgsql@FreeBSD.org
COMMENT=	The contrib utilities from the PostgreSQL distribution

MASTERDIR=	${.CURDIR}/../postgresql10-server

USES=		bison pgsql:${DISTVERSION:C/([0-9]\.?[0-9]).*/\1/g}

BUILD_DIRS=	src/port src/include src/common contrib
INSTALL_DIRS=	contrib

# this port fails to build in parallel
MAKE_JOBS_UNSAFE=	yes

SLAVE_ONLY=	yes
COMPONENT=	-contrib
CONFIGURE_ARGS+=--with-openssl --disable-nls --with-uuid=bsd
LDFLAGS+=	-lpthread -L${PREFIX}/lib

OPTIONS_DEFINE=	DOCS XML
OPTIONS_DEFAULT=XML
OPTIONS_SUB=	yes

XML_LIB_DEPENDS=libxslt.so:textproc/libxslt \
		libxml2.so:textproc/libxml2
XML_CONFIGURE_WITH=	libxml libxslt

post-configure: 
		@cd ${WRKSRC}/src/backend && ${SETENV} ${MAKE_ENV} ${MAKE_CMD} symlinks

post-install:
	@- ${INSTALL_DATA} ${WRKSRC}/contrib/README ${STAGEDIR}${DOCSDIR}/extension/README

.include "${MASTERDIR}/Makefile"
