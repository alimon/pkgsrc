# $NetBSD: Makefile,v 1.39 2017/06/05 14:22:50 ryoon Exp $

DISTNAME=	Data-UUID-1.221
PKGNAME=	p5-${DISTNAME}
PKGREVISION=	2
CATEGORIES=	devel perl5
MASTER_SITES=	${MASTER_SITE_PERL_CPAN:=Data/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://search.cpan.org/dist/Data-UUID/
COMMENT=	Perl module for generating UUIDs
LICENSE=	modified-bsd

#DEPENDS+=		{perl>=5.7.3,p5-Digest-MD5>=0}:../../security/p5-Digest-MD5

USE_LANGUAGES=		c
PERL5_PACKLIST=		auto/Data/UUID/.packlist

OPSYSVARS+=		MAKE_PARAMS
MAKE_PARAMS.Darwin+=	DEFINE=-D_POSIX_C_SOURCE

.include "../../lang/perl5/module.mk"
.include "../../mk/bsd.pkg.mk"
