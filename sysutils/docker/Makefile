PORTNAME=	docker
PORTVERSION=	22.06
DISTVERSIONPREFIX=	v
CATEGORIES=	sysutils

MAINTAINER=	bryan@frimin.fr
COMMENT=	Docker client CLI

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=	go:modules cpe

PLIST_FILES=	bin/docker

USE_GITHUB=	yes
GH_PROJECT=	cli
GH_TAGNAME=	67cc8b1fd88aea06690eaf3e5d56acd68a0178d2

GO_TARGET=	./cmd/docker
GO_BUILDFLAGS=	-ldflags ' -X "github.com/docker/cli/cli/version.GitCommit=${GH_TAGNAME}" -X "github.com/docker/cli/cli/version.Version=${PORTVERSION}"'

GH_TUPLE=       \
		Azure:go-ansiterm:d185dfc1b5a1:azure_go_ansiterm/vendor/github.com/Azure/go-ansiterm \
		Microsoft:go-winio:v0.5.2:microsoft_go_winio/vendor/github.com/Microsoft/go-winio \
		beorn7:perks:v1.0.1:beorn7_perks/vendor/github.com/beorn7/perks \
		cespare:xxhash:v2.1.2:cespare_xxhash_v2/vendor/github.com/cespare/xxhash/v2 \
		containerd:containerd:v1.6.8:containerd_containerd/vendor/github.com/containerd/containerd \
		creack:pty:v1.1.11:creack_pty/vendor/github.com/creack/pty \
		docker:distribution:v2.8.1:docker_distribution/vendor/github.com/docker/distribution \
		docker:go-connections:v0.4.0:docker_go_connections/vendor/github.com/docker/go-connections \
		docker:go-events:e31b211e4f1c:docker_go_events/vendor/github.com/docker/go-events \
		docker:go-metrics:v0.0.1:docker_go_metrics/vendor/github.com/docker/go-metrics \
		docker:go-units:v0.4.0:docker_go_units/vendor/github.com/docker/go-units \
		docker:go:d30aec9fd63c:docker_go/vendor/github.com/docker/go \
		etcd-io:etcd:v3.5.2:etcd_io_etcd/vendor/go.etcd.io/etcd/raft/v3 \
		fvbommel:sortorder:v1.0.2:fvbommel_sortorder/vendor/github.com/fvbommel/sortorder \
		go-yaml:yaml:v2.4.0:go_yaml_yaml/vendor/gopkg.in/yaml.v2 \
		gogo:protobuf:v1.3.2:gogo_protobuf/vendor/github.com/gogo/protobuf \
		golang:crypto:3147a52a75dd:golang_crypto/vendor/golang.org/x/crypto \
		golang:net:fe4d6282115f:golang_net/vendor/golang.org/x/net \
		golang:protobuf:v1.5.2:golang_protobuf/vendor/github.com/golang/protobuf \
		golang:sys:c680a09ffe64:golang_sys/vendor/golang.org/x/sys \
		golang:term:6886f2dfbf5b:golang_term/vendor/golang.org/x/term \
		golang:text:v0.3.7:golang_text/vendor/golang.org/x/text \
		golang:time:1f47c861a9ac:golang_time/vendor/golang.org/x/time \
		golang:xerrors:5ec99f83aff1:golang_xerrors/vendor/golang.org/x/xerrors \
		google:certificate-transparency-go:v1.0.20:google_certificate_transparency_go/vendor/github.com/google/certificate-transparency-go \
		google:go-cmp:v0.5.7:google_go_cmp/vendor/github.com/google/go-cmp \
		google:go-genproto:3a66f561d7aa:google_go_genproto/vendor/google.golang.org/genproto \
		google:shlex:e7afc7fbc510:google_shlex/vendor/github.com/google/shlex \
		gorilla:mux:v1.8.0:gorilla_mux/vendor/github.com/gorilla/mux \
		gotestyourself:gotest.tools:v3.1.0:gotestyourself_gotest_tools/vendor/gotest.tools/v3 \
		grpc:grpc-go:v1.45.0:grpc_grpc_go/vendor/google.golang.org/grpc \
		imdario:mergo:v0.3.12:imdario_mergo/vendor/github.com/imdario/mergo \
		inconshreveable:mousetrap:v1.0.0:inconshreveable_mousetrap/vendor/github.com/inconshreveable/mousetrap \
		klauspost:compress:v1.15.1:klauspost_compress/vendor/github.com/klauspost/compress \
		mattn:go-runewidth:v0.0.13:mattn_go_runewidth/vendor/github.com/mattn/go-runewidth \
		matttproud:golang_protobuf_extensions:c182affec369:matttproud_golang_protobuf_extensions/vendor/github.com/matttproud/golang_protobuf_extensions \
		miekg:pkcs11:v1.1.1:miekg_pkcs11/vendor/github.com/miekg/pkcs11 \
		mitchellh:mapstructure:v1.3.2:mitchellh_mapstructure/vendor/github.com/mitchellh/mapstructure \
		moby:buildkit:v0.10.4:moby_buildkit/vendor/github.com/moby/buildkit \
		moby:moby:b5a0d7a188ac:moby_moby/vendor/github.com/docker/docker \
		moby:moby:v0.6.4:moby_moby_1/vendor/github.com/docker/docker-credential-helpers \
		moby:swarmkit:48dd89375d0a:moby_swarmkit_v2/vendor/github.com/moby/swarmkit/v2 \
		moby:sys:b22ba8a69b30:moby_sys_sequential/vendor/github.com/moby/sys \
		moby:sys:signal/v0.7.0:moby_sys_signal \
		moby:sys:symlink/v0.2.0:moby_sys_symlink \
		moby:term:3f7ff695adc6:moby_term/vendor/github.com/moby/term \
		morikuni:aec:v1.0.0:morikuni_aec/vendor/github.com/morikuni/aec \
		opencontainers:go-digest:v1.0.0:opencontainers_go_digest/vendor/github.com/opencontainers/go-digest \
		opencontainers:image-spec:02efb9a75ee1:opencontainers_image_spec/vendor/github.com/opencontainers/image-spec \
		opencontainers:runc:v1.1.2:opencontainers_runc/vendor/github.com/opencontainers/runc \
		pkg:errors:v0.9.1:pkg_errors/vendor/github.com/pkg/errors \
		prometheus:client_golang:v1.12.1:prometheus_client_golang/vendor/github.com/prometheus/client_golang \
		prometheus:client_model:v0.2.0:prometheus_client_model/vendor/github.com/prometheus/client_model \
		prometheus:common:v0.32.1:prometheus_common/vendor/github.com/prometheus/common \
		prometheus:procfs:v0.7.3:prometheus_procfs/vendor/github.com/prometheus/procfs \
		protocolbuffers:protobuf-go:v1.27.1:protocolbuffers_protobuf_go/vendor/google.golang.org/protobuf \
		rivo:uniseg:v0.2.0:rivo_uniseg/vendor/github.com/rivo/uniseg \
		sirupsen:logrus:v1.8.1:sirupsen_logrus/vendor/github.com/sirupsen/logrus \
		spf13:cobra:v1.5.0:spf13_cobra/vendor/github.com/spf13/cobra \
		spf13:pflag:v1.0.5:spf13_pflag/vendor/github.com/spf13/pflag \
		theupdateframework:notary:bf96a202a09a:theupdateframework_notary/vendor/github.com/theupdateframework/notary \
		tonistiigi:go-rosetta:f79598599c5d:tonistiigi_go_rosetta/vendor/github.com/tonistiigi/go-rosetta \
		xeipuuv:gojsonpointer:02993c407bfb:xeipuuv_gojsonpointer/vendor/github.com/xeipuuv/gojsonpointer \
		xeipuuv:gojsonreference:bd5ef7bd5415:xeipuuv_gojsonreference/vendor/github.com/xeipuuv/gojsonreference \
		xeipuuv:gojsonschema:v1.2.0:xeipuuv_gojsonschema/vendor/github.com/xeipuuv/gojsonschema

post-extract:
	@${RM} -r ${WRKSRC}/vendor/github.com/moby/sys/signal
	@${RLN} ${WRKSRC_moby_sys_signal}/signal ${WRKSRC}/vendor/github.com/moby/sys/signal
	@${RM} -r ${WRKSRC}/vendor/github.com/moby/sys/symlink
	@${RLN} ${WRKSRC_moby_sys_symlink}/symlink ${WRKSRC}/vendor/github.com/moby/sys/symlink

	@${MV} ${WRKSRC}/vendor.mod ${WRKSRC}/go.mod
	@${MV} ${WRKSRC}/vendor.sum ${WRKSRC}/go.sum

.include <bsd.port.mk>
