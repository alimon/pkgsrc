# $NetBSD: Makefile,v 1.20 2017/11/20 15:55:16 fhajny Exp $

DISTNAME=		beats-6.0.0
CATEGORIES=		sysutils
MASTER_SITES=		${MASTER_SITE_GITHUB:=elastic/}
GITHUB_PROJECT=		beats
GITHUB_TAG=		v${PKGVERSION_NOREV}

MAINTAINER=		filip@joyent.com
HOMEPAGE=		https://www.elastic.co/products/beats
COMMENT=		Data Shippers for Elasticsearch
LICENSE=		apache-2.0

EXTRACT_USING=		bsdtar
USE_TOOLS+=		gmake

GO_DIST_BASE=		${PKGBASE}-${GITHUB_TAG:S/v//}
GO_SRCPATH=		github.com/elastic/beats

# Components to build/install
BEATS=			filebeat heartbeat metricbeat packetbeat

CHECK_RELRO_SKIP+=	bin/filebeat
CHECK_RELRO_SKIP+=	bin/heartbeat
CHECK_RELRO_SKIP+=	bin/metricbeat
CHECK_RELRO_SKIP+=	bin/packetbeat

.for beat in ${BEATS}
CONF_FILES+=		share/examples/beats/${beat}.yml			\
				${PKG_SYSCONFDIR}/${beat}.yml
.endfor

BEATS_DIR?=		${VARBASE}/db/beats
BEATS_LOGDIR?=		${VARBASE}/log/beats

FILES_SUBST+=		BEATS_DIR=${BEATS_DIR}
FILES_SUBST+=		BEATS_LOGDIR=${BEATS_LOGDIR}

PKG_SYSCONFSUBDIR=	beats

SMF_INSTANCES+=		${BEATS}

OWN_DIRS+=		${BEATS_DIR} ${BEATS_LOGDIR}

MAKE_ENV+=		GOPATH=${WRKDIR}:${PREFIX}/gopkg
MAKE_ENV+=		CGO_LDFLAGS="-L${BUILDLINK_PREFIX.libpcap}/lib ${COMPILER_RPATH_FLAG}${BUILDLINK_PREFIX.libpcap}/lib"
BUILD_TARGET=		#

INSTALLATION_DIRS+=	bin share/examples/beats

do-build:
.for beat in ${BEATS}
	cd ${WRKSRC}/${beat} && ${BUILD_MAKE_CMD}
.endfor

do-install:
.for beat in ${BEATS}
	${INSTALL_PROGRAM} ${WRKSRC}/${beat}/${beat} ${DESTDIR}${PREFIX}/bin
	${INSTALL_DATA} ${WRKSRC}/${beat}/${beat}.reference.yml			\
		${DESTDIR}${PREFIX}/share/examples/beats
	${INSTALL_DATA} ${WRKSRC}/${beat}/${beat}.yml				\
		${DESTDIR}${PREFIX}/share/examples/beats
.endfor

.include "../../lang/go/go-package.mk"
.include "../../net/libpcap/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
