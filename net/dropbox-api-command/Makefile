PORTNAME=	dropbox-api-command
PORTVERSION=	2.13
PORTEPOCH=	1
CATEGORIES=	net perl5

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Dropbox API wrapper command

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

MY_DEPENDS=	p5-DateTime-Format-Strptime>=0:devel/p5-DateTime-Format-Strptime \
		p5-Encode-Locale>=0:converters/p5-Encode-Locale \
		p5-JSON>=0:converters/p5-JSON \
		p5-Path-Class>=0.26:devel/p5-Path-Class \
		p5-WebService-Dropbox>=2.05:net/p5-WebService-Dropbox
BUILD_DEPENDS=	${MY_DEPENDS}
RUN_DEPENDS=	${MY_DEPENDS}

USE_GITHUB=	yes
GH_ACCOUNT=	s-aska

NO_ARCH=	yes
USES=		perl5 shebangfix
USE_PERL5=	modbuildtiny
bash_CMD=	${SH}
SHEBANG_FILES=	script/upload-to-dropbox

.include <bsd.port.mk>
