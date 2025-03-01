PORTNAME=	libextractor
PORTVERSION=	1.11
PORTREVISION=	2
CATEGORIES=	textproc
MASTER_SITES=	GNU

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Library for keyword extraction

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/COPYING

BUILD_DEPENDS=	tidy-html5>0:www/tidy-html5
LIB_DEPENDS=	libltdl.so:devel/libltdl libogg.so:audio/libogg \
		libtiff.so:graphics/tiff

USES=		cpe gnome iconv jpeg libarchive libtool \
		makeinfo pathfix pkgconfig python
CPE_VENDOR=	gnu

USE_GNOME=	gtk20 gdkpixbuf2
USE_LDCONFIG=	yes

CONFLICTS_INSTALL=	csound outguess # bin/extract

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--with-gtk-version=2 \
		--with-ltdl=${LOCALBASE}
INSTALL_TARGET=	install-strip

CPPFLAGS+=	$$(pkg-config --cflags gtk+-2.0) \
		-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib ${ICONV_LIB}

INFO=		libextractor

OPTIONS_DEFINE=		EXIV2 FFMPEG FLAC GIF GSF GSTREAMER MPEG2 MP4 \
			NLS RPM SMF TIDY VORBIS

OPTIONS_DEFAULT=	EXIV2 FFMPEG FLAC GIF GSF GSTREAMER MPEG2 MP4 \
			RPM SMF TIDY VORBIS

OPTIONS_SUB=		yes

GSF_DESC=		GSF (OLE2 (MS office) support)
RPM_DESC=		RPM package format support
SMF_DESC=		Standard MIDI file support via LibSMF

EXIV2_LIB_DEPENDS=	libexiv2.so:graphics/exiv2
EXIV2_CONFIGURE_ENV=	EXIV2_H="<exiv2/image.hpp>"
EXIV2_CONFIGURE_ENV_OFF=	EXIV2_H=""
FFMPEG_LIB_DEPENDS=	libavcodec.so:multimedia/ffmpeg
FFMPEG_CONFIGURE_ENABLE=	ffmpeg
FLAC_LIB_DEPENDS=	libFLAC.so:audio/flac
FLAC_CONFIGURE_ENV_OFF=ac_cv_lib_FLAC_FLAC__stream_decoder_init_stream=no
GIF_LIB_DEPENDS=	libgif.so:graphics/giflib
GIF_CONFIGURE_ENV_OFF=	ac_cv_lib_gif_DGifOpen=no
GSF_USE=		gnome=libgsf
GSF_CONFIGURE_ENV_OFF=	ac_cv_lib_gsf_1_gsf_init=no
GSTREAMER_USES=		gstreamer
GSTREAMER_CONFIGURE_WITH=	gstreamer
MP4_LIB_DEPENDS=	libmp4v2.so:multimedia/mp4v2
MP4_CONFIGURE_ENV_OFF=	ac_cv_lib_mp4v2_MP4ReadProvider=no
MPEG2_LIB_DEPENDS=	libmpeg2.so:multimedia/libmpeg2
MPEG2_CONFIGURE_ENV_OFF=	ac_cv_lib_mpeg2_mpeg2_init=no
NLS_USES=		gettext-runtime
NLS_CONFIGURE_ENABLE=	nls
RPM_LIB_DEPENDS=	librpm.so:archivers/rpm4
RPM_CONFIGURE_ENV=	ac_cv_lib_rpm_rpmReadPackageFile=yes
RPM_CONFIGURE_ENV_OFF=	ac_cv_lib_rpm_rpmReadPackageFile=no
SMF_LIB_DEPENDS=	libsmf.so:audio/libsmf
SMF_CONFIGURE_ENV_OFF=	ac_cv_lib_smf_smf_load_from_memory=no
TIDY_LIB_DEPENDS=	libtidy.so:www/tidy-lib
TIDY_CONFIGURE_ENV=	TIDY_H="<tidy/tidy.h>"
TIDY_CONFIGURE_ENV_OFF=	TIDY_H=""
VORBIS_LIB_DEPENDS=	libvorbisfile.so:audio/libvorbis
VORBIS_CONFIGURE_ENV_OFF=	ac_cv_lib_vorbisfile_ov_open_callbacks=no

post-patch:
	@${REINPLACE_CMD} -e \
		's|-lstdc++|| ; \
		 s|-lc_r|-pthread| ; \
		 s|<exiv2/image.hpp>|$${EXIV2_H}| ; \
		 s|<tidy/tidy.h>|$${TIDY_H}|' ${WRKSRC}/configure
	@${REINPLACE_CMD} -e 's|tidy/tidybuffio\.h|tidybuffio.h|' \
		${WRKSRC}/src/plugins/html_extractor.c

.include <bsd.port.mk>
