PORTNAME=	docker-buildx
PORTVERSION=	0.9.1
DISTVERSIONPREFIX=	v
CATEGORIES=	sysutils

MAINTAINER=	bryan@frimin.fr
COMMENT=	Docker CLI plugin for extended build capabilities with BuildKit

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	docker:sysutils/docker

USES=	go:modules

PLIST_FILES=	lib/docker/cli-plugins/docker-buildx

USE_GITHUB=	yes
GH_ACCOUNT=	docker
GH_PROJECT=	buildx

GO_TARGET=	./cmd/buildx:${PREFIX}/lib/docker/cli-plugins/docker-buildx
GO_BUILDFLAGS=	-ldflags ' -X "github.com/docker/buildx/version.Version=${PORTVERSION}"'

GH_TUPLE=	\
		Azure:go-ansiterm:d185dfc1b5a1:azure_go_ansiterm/vendor/github.com/Azure/go-ansiterm \
		Azure:go-autorest:a46566dfcbdc:azure_go_autorest_adal \
		Azure:go-autorest:autorest/v0.11.24:azure_go_autorest_autorest \
		Azure:go-autorest:b3a0b30a7423:azure_go_autorest_date \
		Azure:go-autorest:logger/v0.2.1:azure_go_autorest_logger \
		Azure:go-autorest:tracing/v0.6.0:azure_go_autorest_tracing \
		Azure:go-autorest:v14.2.0:azure_go_autorest/vendor/github.com/Azure/go-autorest \
		Microsoft:go-winio:v0.5.2:microsoft_go_winio/vendor/github.com/Microsoft/go-winio \
		agext:levenshtein:v1.2.3:agext_levenshtein/vendor/github.com/agext/levenshtein \
		agl:ed25519:5312a6153412:agl_ed25519/vendor/github.com/agl/ed25519 \
		apparentlymart:go-cidr:v1.0.1:apparentlymart_go_cidr/vendor/github.com/apparentlymart/go-cidr \
		apparentlymart:go-textseg:v12.0.0:apparentlymart_go_textseg_v12/vendor/github.com/apparentlymart/go-textseg/v12 \
		apparentlymart:go-textseg:v13.0.0:apparentlymart_go_textseg_v13/vendor/github.com/apparentlymart/go-textseg/v13 \
		beorn7:perks:v1.0.1:beorn7_perks/vendor/github.com/beorn7/perks \
		bugsnag:bugsnag-go:v1.4.1:bugsnag_bugsnag_go/vendor/github.com/bugsnag/bugsnag-go \
		bugsnag:panicwrap:v1.2.0:bugsnag_panicwrap/vendor/github.com/bugsnag/panicwrap \
		cenkalti:backoff:v2.1.1:cenkalti_backoff/vendor/github.com/cenkalti/backoff \
		cenkalti:backoff:v4.1.2:cenkalti_backoff_v4/vendor/github.com/cenkalti/backoff/v4 \
		cespare:xxhash:v2.1.2:cespare_xxhash_v2/vendor/github.com/cespare/xxhash/v2 \
		cloudflare:cfssl:b94e044bb51e:cloudflare_cfssl/vendor/github.com/cloudflare/cfssl \
		compose-spec:compose-go:v1.4.0:compose_spec_compose_go/vendor/github.com/compose-spec/compose-go \
		containerd:console:v1.0.3:containerd_console/vendor/github.com/containerd/console \
		containerd:containerd:v1.6.6:containerd_containerd/vendor/github.com/containerd/containerd \
		containerd:continuity:v0.3.0:containerd_continuity/vendor/github.com/containerd/continuity \
		containerd:ttrpc:v1.1.0:containerd_ttrpc/vendor/github.com/containerd/ttrpc \
		containerd:typeurl:v1.0.2:containerd_typeurl/vendor/github.com/containerd/typeurl \
		davecgh:go-spew:v1.1.1:davecgh_go_spew/vendor/github.com/davecgh/go-spew \
		distribution:distribution:4bf3547399eb:distribution_distribution_v3/vendor/github.com/distribution/distribution/v3 \
		docker:cli-docs-tool:v0.5.0:docker_cli_docs_tool/vendor/github.com/docker/cli-docs-tool \
		docker:cli:418ca3b4d46f:docker_cli/vendor/github.com/docker/cli \
		docker:distribution:v2.8.1:docker_distribution/vendor/github.com/docker/distribution \
		docker:go-connections:v0.4.0:docker_go_connections/vendor/github.com/docker/go-connections \
		docker:go-metrics:v0.0.1:docker_go_metrics/vendor/github.com/docker/go-metrics \
		docker:go-units:v0.4.0:docker_go_units/vendor/github.com/docker/go-units \
		docker:go:d30aec9fd63c:docker_go/vendor/github.com/docker/go \
		docker:libtrust:9cbd2a1374f4:docker_libtrust/vendor/github.com/docker/libtrust \
		elazarl:goproxy:aa519ddbe484:elazarl_goproxy/vendor/github.com/elazarl/goproxy \
		fatih:pool:v2.0.0:fatih_pool/vendor/gopkg.in/fatih/pool.v2 \
		felixge:httpsnoop:v1.0.2:felixge_httpsnoop/vendor/github.com/felixge/httpsnoop \
		fvbommel:sortorder:v1.0.1:fvbommel_sortorder/vendor/github.com/fvbommel/sortorder \
		go-check:check:10cb98267c6c:go_check_check/vendor/gopkg.in/check.v1 \
		go-inf:inf:v0.9.1:go_inf_inf/vendor/gopkg.in/inf.v0 \
		go-logr:logr:v1.2.2:go_logr_logr/vendor/github.com/go-logr/logr \
		go-logr:stdr:v1.2.2:go_logr_stdr/vendor/github.com/go-logr/stdr \
		go-sql-driver:mysql:v1.6.0:go_sql_driver_mysql/vendor/github.com/go-sql-driver/mysql \
		go-yaml:yaml:v2.4.0:go_yaml_yaml/vendor/gopkg.in/yaml.v2 \
		go-yaml:yaml:v3.0.1:go_yaml_yaml_1/vendor/gopkg.in/yaml.v3 \
		gofrs:flock:v0.7.3:gofrs_flock/vendor/github.com/gofrs/flock \
		gogo:googleapis:v1.4.1:gogo_googleapis/vendor/github.com/gogo/googleapis \
		gogo:protobuf:v1.3.2:gogo_protobuf/vendor/github.com/gogo/protobuf \
		golang-jwt:jwt:v4.2.0:golang_jwt_jwt_v4/vendor/github.com/golang-jwt/jwt/v4 \
		golang:appengine:v1.6.7:golang_appengine/vendor/google.golang.org/appengine \
		golang:crypto:3147a52a75dd:golang_crypto/vendor/golang.org/x/crypto \
		golang:net:cd36cc0744dd:golang_net/vendor/golang.org/x/net \
		golang:oauth2:2bc19b11175f:golang_oauth2/vendor/golang.org/x/oauth2 \
		golang:protobuf:v1.5.2:golang_protobuf/vendor/github.com/golang/protobuf \
		golang:sync:886fb9371eb4:golang_sync/vendor/golang.org/x/sync \
		golang:sys:c0bba94af5f8:golang_sys/vendor/golang.org/x/sys \
		golang:term:03fcf44c2211:golang_term/vendor/golang.org/x/term \
		golang:text:v0.3.7:golang_text/vendor/golang.org/x/text \
		golang:time:90d013bbcef8:golang_time/vendor/golang.org/x/time \
		google:certificate-transparency-go:v1.0.21:google_certificate_transparency_go/vendor/github.com/google/certificate-transparency-go \
		google:go-cmp:v0.5.8:google_go_cmp/vendor/github.com/google/go-cmp \
		google:go-genproto:1973136f34c6:google_go_genproto/vendor/google.golang.org/genproto \
		google:gofuzz:v1.2.0:google_gofuzz/vendor/github.com/google/gofuzz \
		google:shlex:e7afc7fbc510:google_shlex/vendor/github.com/google/shlex \
		google:uuid:v1.3.0:google_uuid/vendor/github.com/google/uuid \
		googleapis:gnostic:v0.5.5:googleapis_gnostic/vendor/github.com/googleapis/gnostic \
		googleapis:google-cloud-go:v0.81.0:googleapis_google_cloud_go/vendor/cloud.google.com/go \
		gorethink:gorethink:v3.0.5:gorethink_gorethink \
		gorilla:mux:v1.8.0:gorilla_mux/vendor/github.com/gorilla/mux \
		grpc-ecosystem:go-grpc-middleware:v1.3.0:grpc_ecosystem_go_grpc_middleware/vendor/github.com/grpc-ecosystem/go-grpc-middleware \
		grpc-ecosystem:grpc-gateway:v1.16.0:grpc_ecosystem_grpc_gateway/vendor/github.com/grpc-ecosystem/grpc-gateway \
		grpc:grpc-go:v1.47.0:grpc_grpc_go/vendor/google.golang.org/grpc \
		hailocab:go-hostpool:e80d13ce29ed:hailocab_go_hostpool/vendor/github.com/hailocab/go-hostpool \
		hashicorp:go-cty-funcs:2721b1e36840:hashicorp_go_cty_funcs/vendor/github.com/hashicorp/go-cty-funcs \
		hashicorp:hcl:v2.8.2:hashicorp_hcl_v2/vendor/github.com/hashicorp/hcl/v2 \
		imdario:mergo:v0.3.13:imdario_mergo/vendor/github.com/imdario/mergo \
		inconshreveable:mousetrap:v1.0.0:inconshreveable_mousetrap/vendor/github.com/inconshreveable/mousetrap \
		jinzhu:gorm:v1.9.2:jinzhu_gorm/vendor/github.com/jinzhu/gorm \
		jinzhu:inflection:04140366298a:jinzhu_inflection/vendor/github.com/jinzhu/inflection \
		json-iterator:go:v1.1.12:json_iterator_go/vendor/github.com/json-iterator/go \
		kardianos:osext:2bc1f35cddc0:kardianos_osext/vendor/github.com/kardianos/osext \
		klauspost:compress:v1.15.7:klauspost_compress/vendor/github.com/klauspost/compress \
		kr:pretty:v0.3.0:kr_pretty/vendor/github.com/kr/pretty \
		kubernetes-sigs:structured-merge-diff:v4.1.2:kubernetes_sigs_structured_merge_diff/vendor/sigs.k8s.io/structured-merge-diff/v4 \
		kubernetes-sigs:yaml:v1.2.0:kubernetes_sigs_yaml/vendor/sigs.k8s.io/yaml \
		kubernetes:api:v0.22.4:kubernetes_api/vendor/k8s.io/api \
		kubernetes:apimachinery:v0.22.4:kubernetes_apimachinery/vendor/k8s.io/apimachinery \
		kubernetes:client-go:v0.22.4:kubernetes_client_go/vendor/k8s.io/client-go \
		kubernetes:klog:v2.30.0:kubernetes_klog/vendor/k8s.io/klog/v2 \
		kubernetes:utils:cb0fa318a74b:kubernetes_utils/vendor/k8s.io/utils \
		mattn:go-shellwords:v1.0.12:mattn_go_shellwords/vendor/github.com/mattn/go-shellwords \
		matttproud:golang_protobuf_extensions:c182affec369:matttproud_golang_protobuf_extensions/vendor/github.com/matttproud/golang_protobuf_extensions \
		miekg:pkcs11:v1.1.1:miekg_pkcs11/vendor/github.com/miekg/pkcs11 \
		mitchellh:go-wordwrap:ad45545899c7:mitchellh_go_wordwrap/vendor/github.com/mitchellh/go-wordwrap \
		mitchellh:mapstructure:v1.5.0:mitchellh_mapstructure/vendor/github.com/mitchellh/mapstructure \
		moby:buildkit:55ba9d14360a:moby_buildkit/vendor/github.com/moby/buildkit \
		moby:locker:v1.0.1:moby_locker/vendor/github.com/moby/locker \
		moby:moby:a60b458179aa:moby_moby/vendor/github.com/docker/docker \
		moby:moby:v0.6.4:moby_moby_1/vendor/github.com/docker/docker-credential-helpers \
		moby:spdystream:v0.2.0:moby_spdystream/vendor/github.com/moby/spdystream \
		moby:sys:signal/v0.6.0:moby_sys_signal/vendor/github.com/moby/sys \
		moby:term:3f7ff695adc6:moby_term/vendor/github.com/moby/term \
		modern-go:concurrent:bacd9c7ef1dd:modern_go_concurrent/vendor/github.com/modern-go/concurrent \
		modern-go:reflect2:v1.0.2:modern_go_reflect2/vendor/github.com/modern-go/reflect2 \
		morikuni:aec:v1.0.0:morikuni_aec/vendor/github.com/morikuni/aec \
		open-telemetry:opentelemetry-go-contrib:zpages/v0.29.0:open_telemetry_opentelemetry_go_contrib/vendor/go.opentelemetry.io/contrib/instrumentation/google.golang.org/grpc/otelgrpc \
		open-telemetry:opentelemetry-go-contrib:zpages/v0.29.0:open_telemetry_opentelemetry_go_contrib_1/vendor/go.opentelemetry.io/contrib/instrumentation/net/http/httptrace/otelhttptrace \
		open-telemetry:opentelemetry-go-contrib:zpages/v0.29.0:open_telemetry_opentelemetry_go_contrib_2/vendor/go.opentelemetry.io/contrib/instrumentation/net/http/otelhttp \
		open-telemetry:opentelemetry-go:metric/v0.27.0:open_telemetry_opentelemetry_go_1/vendor/go.opentelemetry.io/otel/internal/metric \
		open-telemetry:opentelemetry-go:metric/v0.27.0:open_telemetry_opentelemetry_go_2/vendor/go.opentelemetry.io/otel/metric \
		open-telemetry:opentelemetry-go:v1.4.1:open_telemetry_opentelemetry_go/vendor/go.opentelemetry.io/otel \
		open-telemetry:opentelemetry-proto-go:v0.12.0:open_telemetry_opentelemetry_proto_go/vendor/go.opentelemetry.io/proto/otlp \
		opencontainers:go-digest:v1.0.0:opencontainers_go_digest/vendor/github.com/opencontainers/go-digest \
		opencontainers:image-spec:c5a74bcca799:opencontainers_image_spec/vendor/github.com/opencontainers/image-spec \
		opencontainers:runc:v1.1.3:opencontainers_runc/vendor/github.com/opencontainers/runc \
		pelletier:go-toml:v1.9.4:pelletier_go_toml/vendor/github.com/pelletier/go-toml \
		pkg:errors:v0.9.1:pkg_errors/vendor/github.com/pkg/errors \
		pmezard:go-difflib:v1.0.0:pmezard_go_difflib/vendor/github.com/pmezard/go-difflib \
		prometheus:client_golang:v1.12.2:prometheus_client_golang/vendor/github.com/prometheus/client_golang \
		prometheus:client_model:v0.2.0:prometheus_client_model/vendor/github.com/prometheus/client_model \
		prometheus:common:v0.32.1:prometheus_common/vendor/github.com/prometheus/common \
		prometheus:procfs:v0.7.3:prometheus_procfs/vendor/github.com/prometheus/procfs \
		protocolbuffers:protobuf-go:v1.27.1:protocolbuffers_protobuf_go/vendor/google.golang.org/protobuf \
		rogpeppe:go-internal:v1.8.1:rogpeppe_go_internal/vendor/github.com/rogpeppe/go-internal \
		serialx:hashring:8b2912629002:serialx_hashring/vendor/github.com/serialx/hashring \
		sirupsen:logrus:v1.9.0:sirupsen_logrus/vendor/github.com/sirupsen/logrus \
		spf13:cobra:v1.5.0:spf13_cobra/vendor/github.com/spf13/cobra \
		spf13:pflag:v1.0.5:spf13_pflag/vendor/github.com/spf13/pflag \
		stretchr:testify:v1.8.0:stretchr_testify/vendor/github.com/stretchr/testify \
		theupdateframework:notary:v0.6.1:theupdateframework_notary/vendor/github.com/theupdateframework/notary \
		tonistiigi:fsutil:0dbf3a8a7d58:tonistiigi_fsutil/vendor/github.com/tonistiigi/fsutil \
		tonistiigi:units:6950e57a87ea:tonistiigi_units/vendor/github.com/tonistiigi/units \
		tonistiigi:vt100:8066bb97264f:tonistiigi_vt100/vendor/github.com/tonistiigi/vt100 \
		xeipuuv:gojsonpointer:4e3ac2762d5f:xeipuuv_gojsonpointer/vendor/github.com/xeipuuv/gojsonpointer \
		xeipuuv:gojsonreference:bd5ef7bd5415:xeipuuv_gojsonreference/vendor/github.com/xeipuuv/gojsonreference \
		xeipuuv:gojsonschema:v1.2.0:xeipuuv_gojsonschema/vendor/github.com/xeipuuv/gojsonschema \
		zclconf:go-cty:v1.10.0:zclconf_go_cty/vendor/github.com/zclconf/go-cty

post-extract:
	@${RM} -r ${WRKSRC}/vendor/github.com/Azure/go-autorest/autorest
	@${RLN} ${WRKSRC_azure_go_autorest_autorest}/autorest ${WRKSRC}/vendor/github.com/Azure/go-autorest/autorest
	@${RM} -r ${WRKSRC}/vendor/github.com/Azure/go-autorest/autorest/adal
	@${RLN} ${WRKSRC_azure_go_autorest_adal}/autorest/adal ${WRKSRC}/vendor/github.com/Azure/go-autorest/autorest/adal
	@${RM} -r ${WRKSRC}/vendor/github.com/Azure/go-autorest/autorest/date
	@${RLN} ${WRKSRC_azure_go_autorest_date}/autorest/date ${WRKSRC}/vendor/github.com/Azure/go-autorest/autorest/date
	@${RM} -r ${WRKSRC}/vendor/github.com/Azure/go-autorest/logger
	@${RLN} ${WRKSRC_azure_go_autorest_logger}/logger ${WRKSRC}/vendor/github.com/Azure/go-autorest/logger
	@${RM} -r ${WRKSRC}/vendor/github.com/Azure/go-autorest/tracing
	@${RLN} ${WRKSRC_azure_go_autorest_tracing}/tracing ${WRKSRC}/vendor/github.com/Azure/go-autorest/tracing

.include <bsd.port.mk>
