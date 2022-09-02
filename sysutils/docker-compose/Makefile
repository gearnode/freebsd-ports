PORTNAME=	docker-compose
PORTVERSION=	2.10.2
DISTVERSIONPREFIX=	v
CATEGORIES=	sysutils

MAINTAINER=	bryan@frimin.fr
COMMENT=	Define and run multi-container applications with Docker

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	docker:sysutils/docker

USES=	go:modules

PLIST_FILES=	lib/docker/cli-plugins/docker-compose

USE_GITHUB=	yes
GH_ACCOUNT=	docker
GH_PROJECT=	compose

GO_TARGET=	./cmd:${PREFIX}/lib/docker/cli-plugins/docker-compose
GO_BUILDFLAGS=	-ldflags ' -X "github.com/docker/compose/v2/internal.Version=${PORTVERSION}"'

GH_TUPLE=       \
		AlecAivazis:survey:v2.3.5:alecaivazis_survey_v2/vendor/github.com/AlecAivazis/survey/v2 \
		Azure:go-ansiterm:d185dfc1b5a1:azure_go_ansiterm/vendor/github.com/Azure/go-ansiterm \
		Masterminds:semver:v1.5.0:masterminds_semver/vendor/github.com/Masterminds/semver \
		Microsoft:go-winio:v0.5.2:microsoft_go_winio/vendor/github.com/Microsoft/go-winio \
		beorn7:perks:v1.0.1:beorn7_perks/vendor/github.com/beorn7/perks \
		buger:goterm:v1.0.4:buger_goterm/vendor/github.com/buger/goterm \
		cespare:xxhash:v2.1.2:cespare_xxhash_v2/vendor/github.com/cespare/xxhash/v2 \
		cnabio:cnab-go:v0.23.4:cnabio_cnab_go/vendor/github.com/cnabio/cnab-go \
		cnabio:cnab-to-oci:v0.3.6:cnabio_cnab_to_oci/vendor/github.com/cnabio/cnab-to-oci \
		compose-spec:compose-go:v1.5.0:compose_spec_compose_go/vendor/github.com/compose-spec/compose-go \
		containerd:console:v1.0.3:containerd_console/vendor/github.com/containerd/console \
		containerd:containerd:v1.6.8:containerd_containerd/vendor/github.com/containerd/containerd \
		containerd:continuity:d132b287edc8:containerd_continuity/vendor/github.com/containerd/continuity \
		containerd:ttrpc:v1.1.0:containerd_ttrpc/vendor/github.com/containerd/ttrpc \
		containerd:typeurl:v1.0.2:containerd_typeurl/vendor/github.com/containerd/typeurl \
		cyberphone:json-canonicalization:6bc126869bf4:cyberphone_json_canonicalization/vendor/github.com/cyberphone/json-canonicalization \
		davecgh:go-spew:v1.1.1:davecgh_go_spew/vendor/github.com/davecgh/go-spew \
		distribution:distribution:26163d82560f:distribution_distribution_v3/vendor/github.com/distribution/distribution/v3 \
		docker:buildx:v0.8.2:docker_buildx/vendor/github.com/docker/buildx \
		docker:cli-docs-tool:v0.5.0:docker_cli_docs_tool/vendor/github.com/docker/cli-docs-tool \
		docker:cli:2b52f62e9627:docker_cli/vendor/github.com/docker/cli \
		docker:distribution:v2.8.1:docker_distribution/vendor/github.com/docker/distribution \
		docker:go-connections:v0.4.0:docker_go_connections/vendor/github.com/docker/go-connections \
		docker:go-metrics:v0.0.1:docker_go_metrics/vendor/github.com/docker/go-metrics \
		docker:go-units:v0.5.0:docker_go_units/vendor/github.com/docker/go-units \
		docker:go:d30aec9fd63c:docker_go/vendor/github.com/docker/go \
		felixge:httpsnoop:v1.0.2:felixge_httpsnoop/vendor/github.com/felixge/httpsnoop \
		fvbommel:sortorder:v1.0.2:fvbommel_sortorder/vendor/github.com/fvbommel/sortorder \
		go-inf:inf:v0.9.1:go_inf_inf/vendor/gopkg.in/inf.v0 \
		go-logr:logr:v1.2.2:go_logr_logr/vendor/github.com/go-logr/logr \
		go-logr:stdr:v1.2.2:go_logr_stdr/vendor/github.com/go-logr/stdr \
		go-yaml:yaml:v2.4.0:go_yaml_yaml/vendor/gopkg.in/yaml.v2 \
		go-yaml:yaml:v3.0.1:go_yaml_yaml_1/vendor/gopkg.in/yaml.v3 \
		gofrs:flock:v0.8.0:gofrs_flock/vendor/github.com/gofrs/flock \
		gogo:googleapis:v1.4.1:gogo_googleapis/vendor/github.com/gogo/googleapis \
		gogo:protobuf:v1.3.2:gogo_protobuf/vendor/github.com/gogo/protobuf \
		golang:appengine:v1.6.7:golang_appengine/vendor/google.golang.org/appengine \
		golang:crypto:86341886e292:golang_crypto/vendor/golang.org/x/crypto \
		golang:mock:v1.6.0:golang_mock/vendor/github.com/golang/mock \
		golang:net:27dd8689420f:golang_net/vendor/golang.org/x/net \
		golang:oauth2:d3ed0bb246c8:golang_oauth2/vendor/golang.org/x/oauth2 \
		golang:protobuf:v1.5.2:golang_protobuf/vendor/github.com/golang/protobuf \
		golang:sync:886fb9371eb4:golang_sync/vendor/golang.org/x/sync \
		golang:sys:fbc7d0a398ab:golang_sys/vendor/golang.org/x/sys \
		golang:term:03fcf44c2211:golang_term/vendor/golang.org/x/term \
		golang:text:v0.3.7:golang_text/vendor/golang.org/x/text \
		golang:time:90d013bbcef8:golang_time/vendor/golang.org/x/time \
		google:go-cmp:v0.5.8:google_go_cmp/vendor/github.com/google/go-cmp \
		google:go-genproto:57ef72a4c106:google_go_genproto/vendor/google.golang.org/genproto \
		google:gofuzz:v1.2.0:google_gofuzz/vendor/github.com/google/gofuzz \
		google:shlex:e7afc7fbc510:google_shlex/vendor/github.com/google/shlex \
		gorilla:mux:v1.8.0:gorilla_mux/vendor/github.com/gorilla/mux \
		gotestyourself:gotest.tools:v2.2.0:gotestyourself_gotest_tools/vendor/gotest.tools \
		gotestyourself:gotest.tools:v3.3.0:gotestyourself_gotest_tools_1/vendor/gotest.tools/v3 \
		grpc-ecosystem:go-grpc-middleware:v1.3.0:grpc_ecosystem_go_grpc_middleware/vendor/github.com/grpc-ecosystem/go-grpc-middleware \
		grpc-ecosystem:grpc-gateway:v1.16.0:grpc_ecosystem_grpc_gateway/vendor/github.com/grpc-ecosystem/grpc-gateway \
		grpc:grpc-go:v1.45.0:grpc_grpc_go/vendor/google.golang.org/grpc \
		hashicorp:errwrap:v1.1.0:hashicorp_errwrap/vendor/github.com/hashicorp/errwrap \
		hashicorp:go-multierror:v1.1.1:hashicorp_go_multierror/vendor/github.com/hashicorp/go-multierror \
		hashicorp:go-version:v1.6.0:hashicorp_go_version/vendor/github.com/hashicorp/go-version \
		imdario:mergo:v0.3.13:imdario_mergo/vendor/github.com/imdario/mergo \
		inconshreveable:mousetrap:v1.0.0:inconshreveable_mousetrap/vendor/github.com/inconshreveable/mousetrap \
		json-iterator:go:v1.1.12:json_iterator_go/vendor/github.com/json-iterator/go \
		kballard:go-shellquote:95032a82bc51:kballard_go_shellquote/vendor/github.com/kballard/go-shellquote \
		klauspost:compress:v1.15.1:klauspost_compress/vendor/github.com/klauspost/compress \
		kubernetes-sigs:structured-merge-diff:v4.2.1:kubernetes_sigs_structured_merge_diff/vendor/sigs.k8s.io/structured-merge-diff/v4 \
		kubernetes-sigs:yaml:v1.2.0:kubernetes_sigs_yaml/vendor/sigs.k8s.io/yaml \
		kubernetes:api:v0.22.4:kubernetes_api/vendor/k8s.io/api \
		kubernetes:apimachinery:v0.22.4:kubernetes_apimachinery/vendor/k8s.io/apimachinery \
		kubernetes:client-go:v0.22.4:kubernetes_client_go/vendor/k8s.io/client-go \
		kubernetes:klog:v2.60.1:kubernetes_klog/vendor/k8s.io/klog/v2 \
		kubernetes:utils:3a6ce19ff2f9:kubernetes_utils/vendor/k8s.io/utils \
		mattn:go-colorable:v0.1.12:mattn_go_colorable/vendor/github.com/mattn/go-colorable \
		mattn:go-isatty:v0.0.16:mattn_go_isatty/vendor/github.com/mattn/go-isatty \
		mattn:go-shellwords:v1.0.12:mattn_go_shellwords/vendor/github.com/mattn/go-shellwords \
		matttproud:golang_protobuf_extensions:c182affec369:matttproud_golang_protobuf_extensions/vendor/github.com/matttproud/golang_protobuf_extensions \
		mgutz:ansi:9520e82c474b:mgutz_ansi/vendor/github.com/mgutz/ansi \
		miekg:pkcs11:v1.1.1:miekg_pkcs11/vendor/github.com/miekg/pkcs11 \
		mitchellh:mapstructure:v1.5.0:mitchellh_mapstructure/vendor/github.com/mitchellh/mapstructure \
		moby:buildkit:v0.10.4:moby_buildkit/vendor/github.com/moby/buildkit \
		moby:locker:v1.0.1:moby_locker/vendor/github.com/moby/locker \
		moby:moby:83b51522df43:moby_moby/vendor/github.com/docker/docker \
		docker:docker-credential-helpers:v0.6.4:moby_moby_1/vendor/github.com/docker/docker-credential-helpers \
		moby:sys:signal/v0.6.0:moby_sys_signal/vendor/github.com/moby/sys \
		moby:sys:symlink/v0.2.0:moby_sys_symlink \
		moby:term:3f7ff695adc6:moby_term/vendor/github.com/moby/term \
		modern-go:concurrent:bacd9c7ef1dd:modern_go_concurrent/vendor/github.com/modern-go/concurrent \
		modern-go:reflect2:v1.0.2:modern_go_reflect2/vendor/github.com/modern-go/reflect2 \
		morikuni:aec:v1.0.0:morikuni_aec/vendor/github.com/morikuni/aec \
		open-telemetry:opentelemetry-go-contrib:instrumentation/google.golang.org/grpc/otelgrpc/v0.29.0:open_telemetry_opentelemetry_go_contrib/vendor/go.opentelemetry.io/contrib \
		open-telemetry:opentelemetry-go-contrib:instrumentation/net/http/httptrace/otelhttptrace/v0.29.0:open_telemetry_opentelemetry_go_contrib_1/vendor/go.opentelemetry.io/contrib \
		open-telemetry:opentelemetry-go-contrib:instrumentation/net/http/otelhttp/v0.29.0:open_telemetry_opentelemetry_go_contrib_2/vendor/go.opentelemetry.io/contrib/instrumentation/net/http/otelhttp \
		open-telemetry:opentelemetry-go:metric/v0.27.0:open_telemetry_opentelemetry_go_1/vendor/go.opentelemetry.io/otel/internal/metric \
		open-telemetry:opentelemetry-go:metric/v0.27.0:open_telemetry_opentelemetry_go_2/vendor/go.opentelemetry.io/otel/metric \
		open-telemetry:opentelemetry-go:v1.4.1:open_telemetry_opentelemetry_go/vendor/go.opentelemetry.io/otel \
		open-telemetry:opentelemetry-proto-go:v0.12.0:open_telemetry_opentelemetry_proto_go/vendor/go.opentelemetry.io/proto \
		opencontainers:go-digest:v1.0.0:opencontainers_go_digest/vendor/github.com/opencontainers/go-digest \
		opencontainers:image-spec:c5a74bcca799:opencontainers_image_spec/vendor/github.com/opencontainers/image-spec \
		opencontainers:runc:v1.1.2:opencontainers_runc/vendor/github.com/opencontainers/runc \
		pelletier:go-toml:v1.9.4:pelletier_go_toml/vendor/github.com/pelletier/go-toml \
		pkg:errors:v0.9.1:pkg_errors/vendor/github.com/pkg/errors \
		pmezard:go-difflib:v1.0.0:pmezard_go_difflib/vendor/github.com/pmezard/go-difflib \
		prometheus:client_golang:v1.12.1:prometheus_client_golang/vendor/github.com/prometheus/client_golang \
		prometheus:client_model:v0.2.0:prometheus_client_model/vendor/github.com/prometheus/client_model \
		prometheus:common:v0.32.1:prometheus_common/vendor/github.com/prometheus/common \
		prometheus:procfs:v0.7.3:prometheus_procfs/vendor/github.com/prometheus/procfs \
		protocolbuffers:protobuf-go:v1.27.1:protocolbuffers_protobuf_go/vendor/google.golang.org/protobuf \
		qri-io:jsonpointer:v0.1.1:qri_io_jsonpointer/vendor/github.com/qri-io/jsonpointer \
		qri-io:jsonschema:780655b2ba0e:qri_io_jsonschema/vendor/github.com/qri-io/jsonschema \
		sirupsen:logrus:v1.9.0:sirupsen_logrus/vendor/github.com/sirupsen/logrus \
		spf13:cobra:v1.5.0:spf13_cobra/vendor/github.com/spf13/cobra \
		spf13:pflag:v1.0.5:spf13_pflag/vendor/github.com/spf13/pflag \
		stretchr:testify:v1.8.0:stretchr_testify/vendor/github.com/stretchr/testify \
		theupdateframework:notary:v0.7.0:theupdateframework_notary/vendor/github.com/theupdateframework/notary \
		tonistiigi:fsutil:9ed612626da3:tonistiigi_fsutil/vendor/github.com/tonistiigi/fsutil \
		tonistiigi:units:6950e57a87ea:tonistiigi_units/vendor/github.com/tonistiigi/units \
		tonistiigi:vt100:8066bb97264f:tonistiigi_vt100/vendor/github.com/tonistiigi/vt100 \
		xeipuuv:gojsonpointer:02993c407bfb:xeipuuv_gojsonpointer/vendor/github.com/xeipuuv/gojsonpointer \
		xeipuuv:gojsonreference:bd5ef7bd5415:xeipuuv_gojsonreference/vendor/github.com/xeipuuv/gojsonreference \
		xeipuuv:gojsonschema:v1.2.0:xeipuuv_gojsonschema/vendor/github.com/xeipuuv/gojsonschema \
		zmap:zcrypto:4dfcec6e9a8c:zmap_zcrypto/vendor/github.com/zmap/zcrypto \
		zmap:zlint:v1.1.0:zmap_zlint/vendor/github.com/zmap/zlint

post-extract:
	@${RM} -r ${WRKSRC}/vendor/github.com/moby/sys/symlink
	@${RLN} ${WRKSRC_moby_sys_symlink}/symlink ${WRKSRC}/vendor/github.com/moby/sys/symlink

.include <bsd.port.mk>
