PORTNAME=	phpmailer
PORTVERSION=	5.2.28
DISTVERSIONPREFIX=	v
CATEGORIES=	mail

MAINTAINER=	joneum@FreeBSD.org
COMMENT=	Full Featured Email Transfer Class for PHP

LICENSE=	LGPL21
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=		cpe dos2unix php

CONFLICTS_INSTALL=	phpmailer6

PORTSCOUT=	limit:^5\.

USE_GITHUB=	yes
GH_ACCOUNT=	PHPMailer
GH_PROJECT=	PHPMailer

NO_BUILD=	yes
NO_ARCH=	yes

CPE_VENDOR=	phpmailer_project
SUB_FILES=	pkg-message

OPTIONS_DEFINE=	EXAMPLES

do-install:
	@${MKDIR} ${STAGEDIR}${DATADIR}
.for f in PHPMailerAutoload.php class.phpmailer.php class.pop3.php \
	class.smtp.php composer.json
	${INSTALL_DATA} ${WRKSRC}/$f ${STAGEDIR}${DATADIR}
.endfor
.for d in extras language
	@${MKDIR} ${STAGEDIR}${DATADIR}/$d
	${INSTALL_DATA} ${WRKSRC}/$d/* ${STAGEDIR}${DATADIR}/$d
.endfor

do-install-EXAMPLES-on:
	@${MKDIR} ${STAGEDIR}${EXAMPLESDIR}
	@cd ${WRKSRC}/examples && ${COPYTREE_SHARE} . ${STAGEDIR}${EXAMPLESDIR}

.include <bsd.port.mk>
