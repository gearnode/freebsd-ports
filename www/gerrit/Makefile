PORTNAME=	gerrit
DISTVERSION=	3.5.1
CATEGORIES=	www java
MASTER_SITES=	https://gerrit-releases.storage.googleapis.com/
EXTRACT_SUFX=	.war
EXTRACT_ONLY=

MAINTAINER=	bryan@frimin.fr
COMMENT=	Gerrit Code Review

LICENSE=	APACHE20

USE_JAVA=	11

NO_ARCH=	yes
NO_BUILD=	yes

USERS=	${PORTNAME}
GROUPS=	${PORTNAME}

USE_RC_SUBR=    gerrit

RUN_DEPENDS+=	bash:shells/bash \
		git:devel/git

SUB_FILES=	gerrit
SUB_LIST=	GERRIT_USER=${USERS}

do-install:
	${MKDIR} ${STAGEDIR}${DATADIR}/
	${INSTALL_DATA} ${DISTDIR}/${DISTFILES} ${STAGEDIR}${DATADIR}/

.include <bsd.port.mk>
