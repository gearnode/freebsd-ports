PORTNAME=	couchbase
DISTVERSION=	2.6.2
CATEGORIES=	databases

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Couchbase Server PHP extension

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

# Remove these once you have updated this to a version 3.0.5 or later
DEPRECATED=	Requires php 7.4 which is set to expire on 2022-11-29
EXPIRATION_DATE=2022-11-28

BUILD_DEPENDS=	libcouchbase>=2.10.7:databases/libcouchbase
LIB_DEPENDS=	libcouchbase.so:databases/libcouchbase

USES=		php:pecl
USE_PHP=	json:build

IGNORE_WITH_PHP=80 81 82

.include <bsd.port.mk>
