# $NetBSD: Makefile,v 1.15 2017/11/24 22:15:59 wiz Exp $

DISTNAME=	relatorio-0.6.3
PKGNAME=	${PYPKGPREFIX}-${DISTNAME}
CATEGORIES=	textproc python
MASTER_SITES=	${MASTER_SITE_PYPI:=r/relatorio/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://relatorio.tryton.org/
COMMENT=	Templating library able to output odt and pdf files
LICENSE=	gnu-gpl-v3

DEPENDS+=	${PYPKGPREFIX}-genshi>=0.5:../../www/py-genshi
DEPENDS+=	${PYPKGPREFIX}-lxml>=2.0:../../textproc/py-lxml
DEPENDS+=	${PYPKGPREFIX}-pycha-[0-9]*:../../graphics/py-pycha
DEPENDS+=	${PYPKGPREFIX}-yaml-[0-9]*:../../textproc/py-yaml
DEPENDS+=	${PYPKGPREFIX}-cairo-[0-9]*:../../graphics/py-cairo

USE_LANGUAGES=		#none
PYTHON_VERSIONS_INCOMPATIBLE=	34 35 36 # py-gtk2 via py-pycha

.include "../../lang/python/egg.mk"
.include "../../mk/bsd.pkg.mk"
