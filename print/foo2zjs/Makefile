PORTNAME=	foo2zjs
PORTVERSION=	20161203
PORTREVISION=	1
CATEGORIES=	print
MASTER_SITES=	LOCAL/bsam/${PORTNAME} \
		ftp://ftp.wart.ru/pub/FreeBSD/ports/distfiles/

# Obtained from https://www.cybercom.net/~dcoffin/hbpl/
PATCH_SITES=	LOCAL/tijl
PATCHFILES=	hbpl1-20160830.patch.xz:-p1

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Driver for printers that use the ZjStream wire protocol

LICENSE=	GPLv2+
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libcups.so:print/cups
RUN_DEPENDS=	${LOCALBASE}/share/foomatic/db/oldprinterids:print/foomatic-db \
		foomatic-rip:print/cups-filters \
		gsed:textproc/gsed

USES=		cpe ghostscript gmake shebangfix
CPE_VENDOR=	rkkda
SHEBANG_FILES=	msexpand printer-profile.sh

MAKE_JOBS_UNSAFE=	yes

SUB_FILES=	${_DEVDCONF_FILE} pkg-message

OPTIONS_DEFINE=	DOCS

_DEVDCONF_FILE=	${PORTNAME}.conf
_EXTRAFILES=	msexpand getweb

post-patch:
	@${REINPLACE_CMD} -e 's|^CFLAGS|CFLAGS?|g' -e 's|^PREFIX|PREFIX?|g' ${WRKSRC}/icc2ps/Makefile

post-install:
	cd ${WRKSRC} && \
		${INSTALL_SCRIPT} ${_EXTRAFILES} ${STAGEDIR}${PREFIX}/bin
	@${MKDIR} ${STAGEDIR}/etc/devd
	cd ${WRKDIR} && \
		${INSTALL_SCRIPT} ${_DEVDCONF_FILE} ${STAGEDIR}${PREFIX}/etc/devd
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/foo2zjs-icc2ps

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
.for FILE in ChangeLog INSTALL README manual.pdf
	${INSTALL_DATA} ${WRKSRC}/${FILE} ${STAGEDIR}${DOCSDIR}
.endfor

.include <bsd.port.mk>
