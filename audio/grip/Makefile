# $NetBSD: Makefile,v 1.6 2017/11/23 17:19:47 wiz Exp $

DISTNAME=	grip-3.6.1
PKGREVISION=	1
CATEGORIES=	audio
MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=grip/}	

MAINTAINER=	triaxx@NetBSD.org
HOMEPAGE=	https://sourceforge.net/projects/grip/
COMMENT=	CD-player and CD-ripper for the Gnome desktop
LICENSE=	gnu-gpl-v2

USE_TOOLS+=		pkg-config
USE_LIBTOOL=		yes
GNU_CONFIGURE=		yes
USE_LANGUAGES=		c c++

.include "../../audio/grip/options.mk"

.include "../../devel/libgnomeui/buildlink3.mk"
.include "../../graphics/hicolor-icon-theme/buildlink3.mk"
.include "../../x11/vte/buildlink3.mk"
.include "../../www/curl/buildlink3.mk"

.include "../../mk/bsd.pkg.mk"
