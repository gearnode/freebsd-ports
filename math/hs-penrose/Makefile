PORTNAME=	penrose
DISTVERSIONPREFIX=	v
DISTVERSION=	0.1-737
DISTVERSIONSUFFIX=	-gb336c8d
PORTREVISION=	5
CATEGORIES=	math haskell

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Create diagrams by typing mathematical notation in plain text

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	libgfortran.so:lang/gcc${GCC_DEFAULT}

USES=		blaslapack cabal
USE_GITHUB=	yes
USE_CABAL=	MonadRandom-0.5.1.2 \
		SHA-1.6.4.4 \
		StateVar-1.2 \
		ad-4.4 \
		aeson-1.4.7.1_1 \
		alex-3.2.5 \
		ansi-terminal-0.10.3 \
		appar-0.1.8 \
		asn1-encoding-0.9.6_1 \
		asn1-parse-0.9.5 \
		asn1-types-0.3.4 \
		async-2.2.2_1 \
		attoparsec-0.13.2.4 \
		auto-update-0.1.6 \
		base-compat-0.11.1 \
		base-compat-batteries-0.11.1 \
		base-orphans-0.8.2 \
		base64-bytestring-1.0.0.3 \
		basement-0.0.11_2 \
		bifunctors-5.5.7 \
		blaze-builder-0.4.1.0 \
		bsb-http-chunked-0.0.0.4_2 \
		byteorder-1.0.4 \
		bytestring-builder-0.10.8.2.0 \
		cabal-doctest-1.0.8_1 \
		case-insensitive-1.2.1.0 \
		clock-0.8 \
		colour-2.3.5 \
		comonad-5.0.6 \
		contravariant-1.5.2 \
		cookie-0.4.5 \
		cryptohash-md5-0.11.100.1_5 \
		cryptohash-sha1-0.11.100.1_5 \
		cryptonite-0.26 \
		data-default-class-0.1.2.0 \
		data-reify-0.6.1_1 \
		distributive-0.6.2 \
		dlist-0.8.0.8 \
		docopt-0.7.0.5 \
		easy-file-0.2.2 \
		entropy-0.4.1.6 \
		erf-2.0.0.0 \
		exceptions-0.10.4_1 \
		extra-1.7.1 \
		fail-4.9.0.0 \
		fast-logger-3.0.1 \
		free-5.1.3 \
		happy-1.19.12 \
		hashable-1.3.0.0_1 \
		haskell-lexer-1.1 \
		hmatrix-0.20.1 \
		hourglass-0.2.12 \
		hslogger-1.3.1.0_1 \
		hsc2hs-0.68.7 \
		http-date-0.0.8 \
		http-types-0.12.3 \
		http2-2.0.4 \
		integer-logarithms-1.0.3_2 \
		iproute-1.7.9 \
		megaparsec-8.0.0 \
		memory-0.15.0_1 \
		monad-control-1.0.2.3 \
		multimap-1.2.1 \
		nats-1.1.2_3 \
		network-3.1.1.1 \
		network-bsd-2.8.1.0_3 \
		network-byte-order-0.1.4.0 \
		network-info-0.2.0.10_1 \
		old-locale-1.0.0.7_2 \
		old-time-1.1.0.3_2 \
		parser-combinators-1.2.1 \
		pem-0.2.4 \
		pretty-show-1.10 \
		pretty-terminal-0.1.0.0_1 \
		primitive-0.7.0.1 \
		profunctors-5.5.2 \
		psqueues-0.2.7.2_1 \
		random-1.1_1 \
		random-shuffle-0.0.4 \
		reflection-2.1.5 \
		regex-base-0.94.0.0_1 \
		regex-compat-0.95.2.0_1 \
		regex-posix-0.96.0.0_1 \
		resourcet-1.2.3 \
		scientific-0.3.6.2 \
		scotty-0.11.5 \
		semigroupoids-5.3.4 \
		semigroups-0.19.1 \
		simple-sendfile-0.2.30 \
		split-0.2.3.4 \
		storable-complex-0.2.3.0 \
		streaming-commons-0.2.1.2 \
		tagged-0.8.6_2 \
		th-abstraction-0.3.2.0 \
		th-lift-0.8.1 \
		time-compat-1.9.3 \
		time-manager-0.0.0 \
		transformers-base-0.4.5.2 \
		transformers-compat-0.6.5 \
		unix-compat-0.5.2_1 \
		unix-time-0.4.7 \
		unliftio-core-0.2.0.1_1 \
		unordered-containers-0.2.10.0_1 \
		uuid-1.3.13_3 \
		uuid-types-1.0.3_2 \
		vault-0.3.1.4 \
		vector-0.12.1.2 \
		void-0.7.3 \
		wai-3.2.2.1 \
		wai-extra-3.0.29.1 \
		wai-logger-2.3.6 \
		warp-3.3.10 \
		websockets-0.12.7.0 \
		word8-0.1.3 \
		x509-1.7.5_1 \
		zlib-0.6.2.1_1

.include <bsd.port.pre.mk>

.if ${GCC_DEFAULT} >= 10
BROKEN=		fails to build with GCC 10: cabal: Missing dependency on a foreign library: Missing (or bad) C library: gfortran
.endif

.include <bsd.port.post.mk>
