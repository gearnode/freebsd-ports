PORTNAME=	fd
DISTVERSIONPREFIX=	v
DISTVERSION=	8.4.0
PORTREVISION=	1
CATEGORIES=	sysutils
PKGNAMESUFFIX=	-find

MAINTAINER=	mikael@FreeBSD.org
COMMENT=	Simple, fast and user-friendly alternative to find

LICENSE=	APACHE20 MIT
LICENSE_COMB=	dual
LICENSE_FILE_APACHE20=	${WRKSRC}/LICENSE-APACHE
LICENSE_FILE_MIT=	${WRKSRC}/LICENSE-MIT

USES=		cargo
USE_GITHUB=	yes
GH_ACCOUNT=	sharkdp

CARGO_CRATES=	aho-corasick-0.7.18 \
		ansi_term-0.12.1 \
		anyhow-1.0.57 \
		argmax-0.3.0 \
		atty-0.2.14 \
		autocfg-1.1.0 \
		bitflags-1.3.2 \
		bstr-0.2.17 \
		cc-1.0.73 \
		cfg-if-1.0.0 \
		chrono-0.4.19 \
		clap-3.1.18 \
		clap_complete-3.1.4 \
		clap_lex-0.2.0 \
		crossbeam-utils-0.8.8 \
		ctrlc-3.2.2 \
		diff-0.1.12 \
		dirs-next-2.0.0 \
		dirs-sys-next-0.1.2 \
		filetime-0.2.16 \
		fnv-1.0.7 \
		fs_extra-1.2.0 \
		fuchsia-cprng-0.1.1 \
		getrandom-0.2.6 \
		globset-0.4.8 \
		hashbrown-0.11.2 \
		hermit-abi-0.1.19 \
		humantime-2.1.0 \
		ignore-0.4.18 \
		indexmap-1.8.2 \
		jemalloc-sys-0.5.0+5.3.0 \
		jemallocator-0.5.0 \
		lazy_static-1.4.0 \
		libc-0.2.126 \
		log-0.4.17 \
		lscolors-0.10.0 \
		memchr-2.5.0 \
		memoffset-0.6.5 \
		nix-0.23.1 \
		nix-0.24.1 \
		normpath-0.3.2 \
		num-integer-0.1.45 \
		num-traits-0.2.15 \
		num_cpus-1.13.1 \
		once_cell-1.12.0 \
		os_str_bytes-6.1.0 \
		proc-macro-error-1.0.4 \
		proc-macro-error-attr-1.0.4 \
		proc-macro2-1.0.39 \
		quote-1.0.18 \
		rand-0.4.6 \
		rand_core-0.3.1 \
		rand_core-0.4.2 \
		rdrand-0.4.0 \
		redox_syscall-0.2.13 \
		redox_users-0.4.3 \
		regex-1.5.6 \
		regex-syntax-0.6.26 \
		remove_dir_all-0.5.3 \
		same-file-1.0.6 \
		strsim-0.10.0 \
		syn-1.0.95 \
		tempdir-0.3.7 \
		termcolor-1.1.3 \
		terminal_size-0.1.17 \
		test-case-2.1.0 \
		test-case-macros-2.1.0 \
		textwrap-0.15.0 \
		thiserror-1.0.31 \
		thiserror-impl-1.0.31 \
		thread_local-1.1.4 \
		time-0.1.43 \
		unicode-ident-1.0.0 \
		users-0.11.0 \
		version_check-0.9.4 \
		walkdir-2.3.2 \
		wasi-0.10.2+wasi-snapshot-preview1 \
		winapi-0.3.9 \
		winapi-i686-pc-windows-gnu-0.4.0 \
		winapi-util-0.1.5 \
		winapi-x86_64-pc-windows-gnu-0.4.0

MAKE_ENV=	SHELL_COMPLETIONS_DIR=${WRKDIR}/completions

CONFLICTS_INSTALL=	fd

PLIST_FILES=	bin/fd \
		etc/bash_completion.d/fd.bash \
		share/fish/completions/fd.fish \
		share/man/man1/fd.1.gz \
		share/zsh/site-functions/_fd

post-install:
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/fd
	${INSTALL_MAN} ${WRKSRC}/doc/fd.1 \
		${STAGEDIR}${PREFIX}/share/man/man1
	@${MKDIR} ${STAGEDIR}${PREFIX}/etc/bash_completion.d
	${INSTALL_DATA} ${WRKDIR}/completions/fd.bash \
		${STAGEDIR}${PREFIX}/etc/bash_completion.d
	@${MKDIR} ${STAGEDIR}${PREFIX}/share/fish/completions
	${INSTALL_DATA} ${WRKDIR}/completions/fd.fish \
		${STAGEDIR}${PREFIX}/share/fish/completions
	@${MKDIR} ${STAGEDIR}${PREFIX}/share/zsh/site-functions
	${INSTALL_DATA} ${WRKSRC}/contrib/completion/_fd \
		${STAGEDIR}${PREFIX}/share/zsh/site-functions

.include <bsd.port.mk>
