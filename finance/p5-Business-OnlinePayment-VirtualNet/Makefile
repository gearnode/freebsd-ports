PORTNAME=	Business-OnlinePayment-VirtualNet
PORTVERSION=	0.02
PORTREVISION=	3
CATEGORIES=	finance perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Business::OnlinePayment backend module for Vital VirtualNet

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Business-CreditCard>=0:finance/p5-Business-CreditCard \
		p5-Business-OnlinePayment>=0:finance/p5-Business-OnlinePayment \
		p5-TimeDate>=0:devel/p5-TimeDate \
		p5-File-CounterFile>=0:misc/p5-File-CounterFile \
		p5-String-Parity>=0:devel/p5-String-Parity \
		p5-String-LRC>=0:devel/p5-String-LRC

USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
