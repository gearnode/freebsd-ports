PORTNAME=	squirrelmail-translations
PORTVERSION=	20200422
CATEGORIES=	mail www
MASTER_SITES=	http://snapshots.squirrelmail.org/ \
	http://freebsd.uzsolt.hu/src/
PKGNAMESUFFIX=	${PHP_PKGNAMESUFFIX}
DISTNAME=	squirrelmail-${PORTVERSION}_0200-SVN.locales
DIST_SUBDIR=	squirrelmail

MAINTAINER=	uzsolt@uzsolt.hu
COMMENT=	NLS translations for Squirrelmail (mail/squirrelmail)

LICENSE=	GPLv2

RUN_DEPENDS=	squirrelmail${PHP_PKGNAMESUFFIX}>=${PORTVERSION}:mail/squirrelmail@${PHP_FLAVOR}

USES=		tar:bzip2 gettext php:flavors
WRKSRC=		${WRKDIR}/squirrelmail.locales
NO_ARCH=	yes
PORTSCOUT=	ignore:1

# if you were using WITHOUT_WWWDIR, use SQUIRRELDIR=${PREFIX}/squirrelmail
SQUIRRELDIR?=	${PREFIX}/www/squirrelmail
PLIST_SUB=	SQUIRRELDIR="${SQUIRRELDIR:S,^${PREFIX}/,,}"

do-build:
# The en_US help files are included with the main tarball
	@${RM} -r ${WRKSRC}/help/en_US

do-install:
	@${MKDIR} ${STAGEDIR}${SQUIRRELDIR}
	(cd ${WRKSRC} && ${COPYTREE_SHARE} "help images locale" ${STAGEDIR}${SQUIRRELDIR})
	${FIND} ${STAGEDIR}${SQUIRRELDIR} -type d -empty -delete

.include <bsd.port.mk>
