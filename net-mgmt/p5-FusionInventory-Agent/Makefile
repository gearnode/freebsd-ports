PORTNAME=	FusionInventory-Agent
PORTVERSION=	2.5.2
CATEGORIES=	net-mgmt
MASTER_SITES=	CPAN
MASTER_SITE_SUBDIR=	CPAN:GBOUGARD
PKGNAMEPREFIX=	p5-

MAINTAINER=	freebsd@simweb.ch
COMMENT=	Agent for OCS Inventory server and FusionInventory for GLPI servers

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-File-Which>=0:sysutils/p5-File-Which \
		p5-libwww>=0:www/p5-libwww \
		p5-Net-IP>=0:net-mgmt/p5-Net-IP \
		p5-UNIVERSAL-require>=0:devel/p5-UNIVERSAL-require \
		p5-Text-Template>=0:textproc/p5-Text-Template \
		p5-XML-TreePP>=0:textproc/p5-XML-TreePP
TEST_DEPENDS=	p5-File-Copy-Recursive>=0:devel/p5-File-Copy-Recursive \
		p5-POE-Component-Client-Ping>=0:net/p5-POE-Component-Client-Ping \
		p5-HTTP-Proxy>=0:www/p5-HTTP-Proxy \
		p5-HTTP-Server-Simple>=0:www/p5-HTTP-Server-Simple \
		p5-HTTP-Server-Simple-Authen>=0:www/p5-HTTP-Server-Simple-Authen \
		p5-IO-Socket-SSL>=0:security/p5-IO-Socket-SSL \
		p5-IO-Capture>=0:devel/p5-IO-Capture \
		p5-IPC-Run>=0:devel/p5-IPC-Run \
		p5-JSON>=0:converters/p5-JSON \
		p5-Net-SNMP>=0:net-mgmt/p5-Net-SNMP \
		p5-Test-Compile>=0:devel/p5-Test-Compile \
		p5-Test-Deep>=0:devel/p5-Test-Deep \
		p5-Test-Exception>=0:devel/p5-Test-Exception \
		p5-Test-MockModule>=0:devel/p5-Test-MockModule \
		p5-Test-MockObject>=0:devel/p5-Test-MockObject \
		p5-Test-NoWarnings>=0:devel/p5-Test-NoWarnings

CONFLICTS=	p5-FusionInventory-Agent-Task-NetDiscovery \
		p5-FusionInventory-Agent-Task-SNMPQuery

OPTIONS_DEFINE=		CUPS DAEMON DMIDECODE DEPLOY NETDISC NETINV PCIUTILS \
			SSL VMWARE WOL ZLIB
OPTIONS_DEFAULT=	DAEMON PCIUTILS ZLIB
OPTIONS_DEFAULT_aarch64=	DMIDECODE
OPTIONS_DEFAULT_amd64=	DMIDECODE
OPTIONS_DEFAULT_armv6=	DMIDECODE
OPTIONS_DEFAULT_armv7=	DMIDECODE
OPTIONS_DEFAULT_i386=	DMIDECODE
OPTIONS_DEFAULT_riscv64=	DMIDECODE
OPTIONS_DEFAULT_riscv64sf=	DMIDECODE
OPTIONS_SUB=	yes

DAEMON_DESC=	Daemon mode, with opt. web interface
DEPLOY_DESC=	Deployment task
DMIDECODE_DESC=	Dmidecode hardware information
NETDISC_DESC=	Network discovery task
NETINV_DESC=	Network inventory task
PCIUTILS_DESC=	Pciutils hardware information
VMWARE_DESC=	VMware hypervisor remote inventory task
WOL_DESC=	Wake on LAN task
ZLIB_DESC=	Zlib compression

NO_ARCH=	yes
USES=		gmake perl5
USE_PERL5=	configure
USE_RC_SUBR=	fusioninventory

CUPS_RUN_DEPENDS=	p5-Net-CUPS>=0.6:print/p5-Net-CUPS
DAEMON_RUN_DEPENDS=	p5-HTTP-Daemon>=0:www/p5-HTTP-Daemon \
			p5-Proc-Daemon>=0:devel/p5-Proc-Daemon \
			p5-Proc-PID-File>=0:devel/p5-Proc-PID-File
DEPLOY_RUN_DEPENDS=	p5-Archive-Extract>=0:archivers/p5-Archive-Extract \
			p5-SHA>=0:security/p5-SHA \
			p5-File-Copy-Recursive>=0:devel/p5-File-Copy-Recursive \
			p5-JSON>=0:converters/p5-JSON \
			p5-Parallel-ForkManager>=0:devel/p5-Parallel-ForkManager \
			p5-POE-Component-Client-Ping>=0:net/p5-POE-Component-Client-Ping \
			p5-URI-Escape-XS>=0:www/p5-URI-Escape-XS
# Wants URI::Escape, ports tree has URI::Escape::XS, seems drop-in replacement
DMIDECODE_RUN_DEPENDS=	dmidecode:sysutils/dmidecode
NETDISC_RUN_DEPENDS=	nmap:security/nmap \
			p5-Net-NBName>=0:net/p5-Net-NBName \
			p5-Net-SNMP>=0:net-mgmt/p5-Net-SNMP
NETINV_RUN_DEPENDS=	p5-Crypt-DES>=0:security/p5-Crypt-DES \
			p5-Net-SNMP>=0:net-mgmt/p5-Net-SNMP
PCIUTILS_RUN_DEPENDS+=	lspci:sysutils/pciutils
SSL_RUN_DEPENDS=	p5-IO-Socket-SSL>=1.14:security/p5-IO-Socket-SSL \
			p5-LWP-Protocol-https>=0:www/p5-LWP-Protocol-https
WOL_RUN_DEPENDS=	p5-Net-Write>=0:net/p5-Net-Write

post-patch:
	@${FIND} ${WRKSRC} -type f \( -name '*.orig' \) -delete

.include <bsd.port.mk>
