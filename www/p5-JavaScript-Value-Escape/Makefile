# $NetBSD: Makefile,v 1.9 2017/06/05 14:25:24 ryoon Exp $
#

DISTNAME=	JavaScript-Value-Escape-0.07
PKGNAME=	p5-${DISTNAME}
PKGREVISION=	2
CATEGORIES=	textproc perl5
MASTER_SITES=	${MASTER_SITE_PERL_CPAN:=JavaScript/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://search.cpan.org/dist/JavaScript-Value-Escape/
COMMENT=	Avoid XSS with JavaScript value interpolation
LICENSE=	${PERL5_LICENSE}

PERL5_PACKLIST=		auto/JavaScript/Value/Escape/.packlist
PERL5_MODULE_TYPE=	Module::Build

.include "../../lang/perl5/module.mk"
.include "../../mk/bsd.pkg.mk"
