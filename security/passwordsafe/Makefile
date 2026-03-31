# Created by: J Adams <jfa63@duck.com>
PORTNAME=		passwordsafe
PORTVERSION=	1.23.0
CATEGORIES=		security x11
DISTNAME=		passwordsafe-1.23

MAINTAINER=		jfa63@duck.com
COMMENT=		Password Safe - popular secure and convenient password manager
WWW=			https://www.pwsafe.org/

LICENSE=		ART20
LICENSE_FILE=	${WRKSRC}/LICENSE

USE_GITHUB=		yes
GH_ACCOUNT=		pwsafe
GH_PROJECT=		pwsafe
GH_TAGNAME=		${DISTVERSION}

USES=			cmake:noninja compiler:c++17-lang gettext-tools pkgconfig
USE_WX=			3.2
WX_COMPS=		wx
USES+=			gmake
USES+=			ssl
USE_XORG=		x11 xt xtst

DATADIR=		${PREFIX}/share/pwsafe

LIB_DEPENDS=	libcurl.so:ftp/curl \
				libqrencode.so:graphics/libqrencode \
				libuuid.so:misc/libuuid \
				libxerces-c-3.3.so:textproc/xerces-c3
LIB_DEPENDS+=	libX11.so:x11/libX11 \
				libXtst.so:x11/libXtst


# We’ll likely need to set CMAKE args once we see upstream options.
# CMAKE_ARGS+=  ...

post-install:
	@${MV} ${STAGEDIR}${PREFIX}/bin/pwsafe ${STAGEDIR}${PREFIX}/bin/pwsafe-gui || ${TRUE}

.include <bsd.port.mk>
