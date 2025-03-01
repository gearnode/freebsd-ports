PORTNAME=	lablgtk2
PORTVERSION=	2.18.12
CATEGORIES=	x11-toolkits
PKGNAMEPREFIX=	ocaml-

MAINTAINER=	danfe@FreeBSD.org
COMMENT=	Objective Caml interface to GTK+ 2.x

LICENSE=	LGPL21
LICENSE_FILE=	${WRKSRC}/COPYING

USES=		gmake gnome pkgconfig
USE_GNOME=	cairo gdkpixbuf2 gtk20
USE_OCAML=	yes
USE_OCAML_FINDLIB=	yes
USE_OCAML_CAMLP4=	yes
USE_OCAML_LDCONFIG=	yes
USE_OCAML_WASH=		yes

HAS_CONFIGURE=	yes
ALL_TARGET=	all opt
MAKE_JOBS_UNSAFE=	yes

USE_GITHUB=	yes
GH_ACCOUNT=	garrigue
GH_PROJECT=	lablgtk

PORTSCOUT=	limit:^${PORTVERSION:R:R}

CONFIGURE_ARGS=	--prefix=${PREFIX} --with-libdir=${PREFIX}/${OCAML_LIBDIR} \
		--without-gtksourceview --without-gnomeui \
		--without-panel --without-gnomecanvas
CONFIGURE_ENV=	CAMLP4O="camlp4 pa_o.cmo pa_op.cmo pr_dump.cmo"

DOCSDIR=	${OCAML_DOCSDIR}/${PORTNAME}
PORTDOCS=	COPYING README
EXAMPLESDIR=	${OCAML_EXAMPLESDIR}/${PORTNAME}
PORTEXAMPLES=	*

OPTIONS_DEFINE=	DOCS EXAMPLES GLADE GTKGLAREA GTKSOURCEVIEW2 GTKSPELL LIBRSVG2
OPTIONS_DEFAULT=	GLADE GTKGLAREA GTKSOURCEVIEW2 GTKSPELL LIBRSVG2
OPTIONS_SUB=	yes

GTKGLAREA_DESC=	GtkGLArea support
GTKSOURCEVIEW2_DESC=	GtkSourceView 2 support
GTKSPELL_DESC=	GtkSpell support

GLADE_CONFIGURE_WITH=glade
GLADE_USE=	GNOME=libglade2
GLADE_VARS=	EXAMPLES_SUBDIRS+=glade

GTKGLAREA_BUILD_DEPENDS=lablgl:graphics/ocaml-lablgl
GTKGLAREA_LIB_DEPENDS=	libgtkgl-2.0.so:x11-toolkits/gtkglarea2
GTKGLAREA_RUN_DEPENDS=	lablgl:graphics/ocaml-lablgl
GTKGLAREA_CONFIGURE_WITH=gl
GTKGLAREA_VARS=		EXAMPLES_SUBDIRS+=GL

GTKSOURCEVIEW2_CONFIGURE_WITH=gtksourceview2
GTKSOURCEVIEW2_USE=	GNOME=gtksourceview2
GTKSOURCEVIEW2_VARS=	EXAMPLES_SUBDIRS+=sourceview

GTKSPELL_LIB_DEPENDS=	libgtkspell.so:textproc/gtkspell
GTKSPELL_CONFIGURE_WITH=gtkspell

LIBRSVG2_CONFIGURE_WITH=rsvg
LIBRSVG2_USE=		GNOME=librsvg2
LIBRSVG2_VARS=		EXAMPLES_SUBDIRS+=rsvg

PATTERN=	[[:space:]]*(do|then)?[[:space:]]*)cp([[:space:]]

post-patch:
	@${REINPLACE_CMD} -E \
		-e 's|^(CFLAGS[[:space:]]*\+=[[:space:]]*-O)|\1 ${CFLAGS}|' \
		-e 's,^(${PATTERN}+.*INSTALLDIR),\1\$${BSD_INSTALL_DATA} \3,' \
		-e 's,^(${PATTERN}+.*BINDIR),\1\$${BSD_INSTALL_SCRIPT} \3,' \
		-e 's,^(${PATTERN}+.*LIBDIR),\1\$${BSD_INSTALL_DATA} \3,' \
		-e 's,(touch)( "\$$\(DESTDIR\)\$$\(OCAMLLDCONF\)"),${TRUE}\2,' \
		-e 's,(-ldconf )("\$$\(DESTDIR\)\$$\(OCAMLLDCONF\)"),\1ignore,' \
		${WRKSRC}/src/Makefile

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${PORTDOCS:S,^,${WRKSRC}/,} ${STAGEDIR}${DOCSDIR}

post-install-EXAMPLES-on:
	@${MKDIR} ${STAGEDIR}${EXAMPLESDIR}
	@cd ${WRKSRC}/examples && ${COPYTREE_SHARE} \
	"*.ml *.png *.rgb *.xpm text ${EXAMPLES_SUBDIRS}" \
		${STAGEDIR}${EXAMPLESDIR}

.include <bsd.port.mk>
