PORTNAME=	Samba-LDAP
PORTVERSION=	0.05
PORTREVISION=	2
CATEGORIES=	net perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Manage a Samba PDC with an LDAP Backend

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Digest-SHA1>=0:security/p5-Digest-SHA1 \
		p5-List-MoreUtils>=0:lang/p5-List-MoreUtils \
		p5-Readonly>=0:devel/p5-Readonly \
		p5-Class-Base>=0:devel/p5-Class-Base \
		p5-Config-Tiny>=0:devel/p5-Config-Tiny \
		p5-Crypt-SmbHash>=0:security/p5-Crypt-SmbHash \
		p5-perl-ldap>=0:net/p5-perl-ldap \
		p5-Regexp-DefaultFlags>=0:textproc/p5-Regexp-DefaultFlags \
		p5-UNIVERSAL-require>=0:devel/p5-UNIVERSAL-require \
		p5-Unicode-MapUTF8>=0:converters/p5-Unicode-MapUTF8

USES=		perl5
USE_PERL5=	configure

post-patch:
		@${REINPLACE_CMD} -i '' -e '/auto_install/d' ${WRKSRC}/Makefile.PL

.include <bsd.port.mk>
