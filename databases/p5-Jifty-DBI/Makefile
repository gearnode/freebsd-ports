PORTNAME=	Jifty-DBI
PORTVERSION=	0.78
CATEGORIES=	databases perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Object-relational persistence Perl framework

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Cache-Memcached>=0:databases/p5-Cache-Memcached \
		p5-Cache-Simple-TimedExpiry>=0.21:devel/p5-Cache-Simple-TimedExpiry \
		p5-Class-Accessor>=0:devel/p5-Class-Accessor \
		p5-Class-Data-Inheritable>=0:devel/p5-Class-Data-Inheritable \
		p5-Class-ReturnValue>=0.40:devel/p5-Class-ReturnValue \
		p5-Class-Trigger>=0.12:devel/p5-Class-Trigger \
		p5-Clone>=0:devel/p5-Clone \
		p5-DBD-SQLite>=1.14:databases/p5-DBD-SQLite \
		p5-DBI>=0:databases/p5-DBI \
		p5-DBIx-DBSchema>=0.34:databases/p5-DBIx-DBSchema \
		p5-Data-Page>=2.0:databases/p5-Data-Page \
		p5-DateTime-Format-ISO8601>=0:devel/p5-DateTime-Format-ISO8601 \
		p5-DateTime-Format-Strptime>=0:devel/p5-DateTime-Format-Strptime \
		p5-DateTime>=0.34:devel/p5-DateTime \
		p5-Exporter-Lite>=0:devel/p5-Exporter-Lite \
		p5-Hash-Merge>=0:textproc/p5-Hash-Merge \
		p5-Lingua-EN-Inflect>=0:textproc/p5-Lingua-EN-Inflect \
		p5-Object-Declare>=0.22:devel/p5-Object-Declare \
		p5-Scalar-Defer>=0.10:devel/p5-Scalar-Defer \
		p5-Time-Duration-Parse>=0.06:devel/p5-Time-Duration-Parse \
		p5-Time-Duration>=0:devel/p5-Time-Duration \
		p5-UNIVERSAL-require>=0.11:devel/p5-UNIVERSAL-require \
		p5-URI>=0:net/p5-URI \
		p5-YAML-Syck>=0:textproc/p5-YAML-Syck
TEST_DEPENDS=	p5-Test-Warn>=0.1:devel/p5-Test-Warn

NO_ARCH=	yes
USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
