PORTNAME=	pd
DISTVERSION=	0.47-1
PORTREVISION=	1
DISTVERSIONSUFFIX=	.src
CATEGORIES=	audio
MASTER_SITES=	http://msp.ucsd.edu/Software/

MAINTAINER=	brittlehaus@gmail.com
COMMENT=	MIDI-capable real-time audio processor/synthesizer

LICENSE=	BSD3CLAUSE LGPL21
LICENSE_COMB=	multi
LICENSE_FILE_BSD3CLAUSE=	${WRKSRC}/LICENSE.txt

BROKEN_FreeBSD_13=	ld: error: duplicate symbol: glist_reloadingabstraction
BROKEN_FreeBSD_14=	ld: error: duplicate symbol: glist_reloadingabstraction

RUN_DEPENDS=	xdg-open:devel/xdg-utils \
		dejavu>0:x11-fonts/dejavu

WRKSRC=		${WRKDIR}/${DISTNAME:S,${DISTVERSIONSUFFIX},,}

USES=		autoreconf gettext gmake libtool pkgconfig shebangfix \
		tcl:wrapper tk:wrapper
SHEBANG_FILES=	tcl/pkg_mkIndex.tcl
SHEBANG_LANG=	tclsh
tclsh_CMD=	${LOCALBASE}/bin/tclsh
GNU_CONFIGURE=	yes
CONFIGURE_ENV=	ac_cv_lib_pthread_pthread_create=no

CPPFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib -pthread

DESKTOP_ENTRIES="Pd" "" "${PREFIX}/lib/pd/tcl/pd.ico" "pd" "" false

OPTIONS_DEFINE=		ALSA DOCS JACK
OPTIONS_DEFAULT=	JACK

ALSA_CONFIGURE_ENABLE=	alsa
ALSA_LIB_DEPENDS=	libasound.so:audio/alsa-lib
JACK_CONFIGURE_ENABLE=	jack
JACK_LIB_DEPENDS=	libjack.so:audio/jack

post-patch:
	${FIND} ${PATCH_WRKSRC} -name "*.[ch]" | ${XARGS} ${REINPLACE_CMD} -e \
		's|__FreeBSD_kernel__|__FreeBSD__|g ; \
		 s|__x86_64__|__amd64__|g'
	${FIND} ${WRKSRC}/extra -name "*.c" | ${XARGS} ${REINPLACE_CMD} -e \
		 's|<alloca\.h>|<stdlib.h>|g'
	${REINPLACE_CMD} -e \
		's|\*kfreebsd\*gnu\*)|*freebsd*)| ; \
		 s|portaudio=yes|portaudio=no| ; \
		 s|-O3||' ${WRKSRC}/configure.ac
	${REINPLACE_CMD} -e \
		'/^pkgconfigdir/s|=.*|= $$(prefix)/libdata/pkgconfig| ; \
		 /^libpddir/s|=.*|= $$(pkglibdir)| ; \
		 s|make -C|$$(MAKE) -C|' ${WRKSRC}/Makefile.am
	${REINPLACE_CMD} -e \
		'/^pd_LDADD/s| =.*| = $$(LIBM)|' ${WRKSRC}/src/Makefile.am
	${REINPLACE_CMD} -e \
		's|PD_BASEDIR/LICENSE|${DOCSDIR}/LICENSE|g ; \
		 s|PD_BASEDIR/doc/1|${DOCSDIR}/1|g' \
			${WRKSRC}/doc/1.manual/1.introduction.txt
	${REINPLACE_CMD} -e \
		's|-O2 | | ; \
		 s|-lc ||g' ${WRKSRC}/extra/makefile.subdir
	${REINPLACE_CMD} -e \
		'/libpthread/s|_ERROR|_WARN|' ${WRKSRC}/portaudio/configure.in

do-install:
.for i in src man tcl po extra
	(cd ${WRKSRC}/${i} && ${SETENV} ${MAKE_ENV} ${MAKE_CMD} \
		${MAKE_FLAGS} ${MAKEFILE} ${MAKE_ARGS} ${INSTALL_TARGET})
.endfor
	(cd ${WRKSRC} && ${INSTALL_DATA} pd.pc \
		${STAGEDIR}${PREFIX}/libdata/pkgconfig)
	${MKDIR} ${STAGEDIR}${DOCSDIR}
	(${TAR} -C ${WRKSRC}/doc --exclude "*.bak" --exclude "*.orig" \
		-cf - . | ${TAR} -C ${STAGEDIR}${DOCSDIR} --unlink -xf -)
.for i in LICENSE.txt README.txt
	(cd ${WRKSRC} && ${INSTALL_DATA} ${i} ${STAGEDIR}${DOCSDIR})
.endfor
	${LN} -sf ../../${DOCSDIR_REL} ${STAGEDIR}${PREFIX}/lib/pd/doc
	${FIND} ${STAGEDIR}${PREFIX}/lib/pd -name "*.pd_linux" | ${XARGS} \
		${STRIP_CMD}

.include <bsd.port.mk>
