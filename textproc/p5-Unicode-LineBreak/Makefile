PORTNAME=	Unicode-LineBreak
PORTVERSION=	2019.001
CATEGORIES=	textproc perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

# blanket update approval granted.
MAINTAINER=	Olivier.Girard@univ-angers.fr
COMMENT=	Unicode-LineBreak package

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-MIME-Charset>=1.006.2:mail/p5-MIME-Charset

MAKE_JOBS_UNSAFE=	yes

USES=		perl5
USE_PERL5=	configure

CONFIGURE_ARGS=	--with-bundled-sombok

OPTIONS_DEFINE=	THAI
OPTIONS_DEFAULT=THAI

THAI_DESC=	Thai word segmentation support through libthai
THAI_USES=	pkgconfig
THAI_LIB_DEPENDS=	libthai.so:devel/libthai
THAI_CONFIGURE_OFF=	--disable-libthai

post-install:
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/${SITE_ARCH_REL}/auto/Unicode/LineBreak/LineBreak.so

.include <bsd.port.mk>
