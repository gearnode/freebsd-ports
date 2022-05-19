PORTNAME=	pgcopydb
DISTVERSIONPREFIX=	v
DISTVERSION=	0.8
CATEGORIES=	databases

MAINTAINER=	bryan@frimin.fr
COMMENT=	Copy a Postgres database to a target Postgres server

LICENSE=	PostgreSQL
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	liblz4.so:archivers/liblz4 \
		libedit.so:devel/libedit \
		libicudata.so:devel/icu \
		libreadline.so:devel/readline \
		libxml2.so:textproc/libxml2 \
		libxslt.so:textproc/libxslt \
		libintl.so:devel/gettext-runtime \
		libpq.so.${PGSQL${PGSQL_VER_NODOT}_LIBVER}:databases/postgresql${PGSQL_VER_NODOT}-client

USES=	gmake pkgconfig pgsql:14 python:build
WANT_PGSQL=	server

USE_GITHUB=	yes
GH_ACCOUNT=	dimitri
GH_PROJECT=	pgcopydb

OPTIONS_DEFINE=	MANPAGES

OPTIONS_DEFAULT=	MANPAGES

MANPAGES_BUILD_DEPENDS= ${LOCALBASE}/bin/sphinx-build:textproc/py-sphinx@${PY_FLAVOR} \
			${PYTHON_PKGNAMEPREFIX}sphinx_rtd_theme>0:textproc/py-sphinx_rtd_theme@${PY_FLAVOR}

PORTMANS=	pgcopydb\ clone.1 pgcopydb\ dump.1 pgcopydb\ fork.1 \
		pgcopydb\ restore.1 pgcopydb\ stream.1 pgcopydb\ copy.1 \
		pgcopydb\ follow.1 pgcopydb\ list.1 pgcopydb\ snapshot.1 \
		pgcopydb.1

# this port fails to build in parallel
MAKE_JOBS_UNSAFE=	yes

do-build-MANPAGES-on:
	@cd ${WRKSRC} && ${GMAKE} docs

do-install-MANPAGES-on:
.for i in ${PORTMANS}
	${INSTALL_MAN} ${WRKSRC}/docs/_build/man/$i ${STAGEDIR}${PREFIX}/man/man1
.endfor
	${INSTALL_MAN} ${WRKSRC}/docs/_build/man/pgcopydb.5 ${STAGEDIR}${PREFIX}/man/man5

.include <bsd.port.mk>
