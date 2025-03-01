PORTNAME=	gromacs
DISTVERSION=	2022.2
CATEGORIES=	science
MASTER_SITES=	ftp://ftp.gromacs.org/pub/gromacs/

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Compute molecular dynamics

LICENSE=	LGPL21
LICENSE_FILE=	${WRKSRC}/COPYING

BROKEN_i386=	undefined reference to `__atomic_load' and `__atomic_compare_exchange' #`

BUILD_DEPENDS=	boost-libs>=1.44:devel/boost-libs
LIB_DEPENDS=	libhwloc.so:devel/hwloc2

USES=		cmake compiler:c++17-lang fortran gnome perl5 pkgconfig python:build shebangfix xorg
USE_GNOME=	libxml2
USE_LDCONFIG=	yes

SHEBANG_FILES=	admin/*.sh scripts/*.pl scripts/*.sh src/gromacs/selection/*.sh
bash_CMD=	${SH}

CMAKE_OFF=	GMX_USE_RDTSCP \
		USE_PYTHON_SCRIPTS
CMAKE_ARGS=	-DPython3_EXECUTABLE=${PYTHON_CMD}

OPTIONS_DEFINE=		ATLAS FLOAT LEGACY OPENCL OPENMP SIMD X11
OPTIONS_SINGLE=		MP
OPTIONS_SINGLE_MP=	NOMP MPICH OPENMPI THREAD_MPI
OPTIONS_DEFAULT=	LEGACY OPENMP THREAD_MPI X11 # FLOAT should not a default because science/votca needs double precision. This is likely the same for many other uses.
OPTIONS_SUB=		yes

ATLAS_DESC=		Use ATLAS for BLAS and LAPACK
ATLAS_USES=		blaslapack:atlas
ATLAS_USES_OFF=		blaslapack
ATLAS_CMAKE_ON=		-DBLAS_LIBRARIES:FILEPATH="${LOCALBASE}/lib/libcblas.so;${LOCALBASE}/lib/libf77blas.so" \
			-DLAPACK_LIBRARIES:FILEPATH="${LOCALBASE}/lib/libalapack.so"
ATLAS_CMAKE_OFF=	-DBLAS_LIBRARIES:FILEPATH="${LOCALBASE}/lib/libblas.so" \
			-DLAPACK_LIBRARIES:FILEPATH="${LOCALBASE}/lib/liblapack.so"

FLOAT_DESC=		Use single instead of double precision
FLOAT_BUILD_DEPENDS=	fftw3>0:math/fftw3
FLOAT_LIB_DEPENDS=	libfftw3f.so:math/fftw3-float
FLOAT_LIB_DEPENDS_OFF=	libfftw3.so:math/fftw3
FLOAT_CMAKE_ON=		-DGMX_DOUBLE:BOOL=OFF
FLOAT_CMAKE_OFF=	-DGMX_DOUBLE:BOOL=ON
FLOAT_PLIST_SUB=	SUFFIX_D=""
FLOAT_PLIST_SUB_OFF=	SUFFIX_D="_d"

LEGACY_DESC=		Install legacy API # expected by science/votca
LEGACY_CMAKE_BOOL=	GMX_INSTALL_LEGACY_API

OPENCL_CMAKE_BOOL=	GMX_USE_OPENCL
OPENCL_CMAKE_ON=	-DGMX_GPU:STRING=OpenCL # one of: OFF, CUDA, OpenCL, SYCL
OPENCL_CMAKE_OFF=	-DGMX_GPU:STRING=OFF
OPENCL_LIB_DEPENDS=	libOpenCL.so:devel/ocl-icd

OPENMP_CMAKE_ON=	-DGMX_CXX11:BOOL=OFF
OPENMP_CMAKE_OFF=	-DGMX_OPENMP:BOOL=OFF

SIMD_CMAKE_OFF=		-DGMX_SIMD:STRING="None"

X11_USE=		XORG=ice,sm,xext,x11
X11_CMAKE_BOOL=		GMX_X11

MP_DESC=		Multiprocessing

NOMP_DESC=		No multiprocessing support
NOMP_PLIST_SUB=		SUFFIX_MPI=""

MPICH_LIB_DEPENDS=	libmpich.so:net/mpich
MPICH_CMAKE_ON=		-DGMX_MPI:BOOL=ON \
			-DMPI_C_COMPILER:FILEPATH="${LOCALBASE}/bin/mpicc"
MPICH_PLIST_SUB=	SUFFIX_MPI="_mpi"

OPENMPI_BUILD_DEPENDS=	openmpi>0:net/openmpi
OPENMPI_RUN_DEPENDS=	openmpi>0:net/openmpi
OPENMPI_CMAKE_ON=	-DGMX_MPI:BOOL=ON \
			-DMPI_C_COMPILER:FILEPATH="${LOCALBASE}/mpi/openmpi/bin/mpicc"
OPENMPI_PLIST_SUB=	SUFFIX_MPI="_mpi"

THREAD_MPI_DESC=	Build a thread-MPI-based multithreaded version of GROMACS
THREAD_MPI_CMAKE_BOOL=	GMX_THREAD_MPI
THREAD_MPI_PLIST_SUB=	SUFFIX_MPI=""

post-patch:
	@${FIND} ${WRKSRC} -name "CMakeLists.txt" | ${XARGS} \
		${REINPLACE_CMD} -e \
		's|share/man|man| ; \
		 /pkgconfig/s|LIB_INSTALL_DIR}|CMAKE_INSTALL_PREFIX}/libdata|'
	@${FIND} ${WRKSRC} -name "GMXRC.*" | ${XARGS} ${REINPLACE_CMD} -e \
		's|LDLIB/pkgconfig|LDLIB/../libdata/pkgconfig| ; \
		 s|LDLIB}/pkgconfig|LDLIB}/../libdata/pkgconfig|'
	@${REINPLACE_CMD} -e '/CMAKE_REQUIRED_LIBRARIES/d' \
		${WRKSRC}/cmake/gmxTestdlopen.cmake

.include <bsd.port.mk>
