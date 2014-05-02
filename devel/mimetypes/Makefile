# $FreeBSD$

PORTNAME=	mimetypes
PORTVERSION=	1.0
CATEGORIES=	devel

MAINTAINER=	undefined
COMMENT=	Erlang MIME types library

BUILD_DEPENDS=	erlc:${PORTSDIR}/lang/erlang \
		rebar:${PORTSDIR}/devel/rebar
RUN_DEPENDS=	erl:${PORTSDIR}/lang/erlang

PLIST_SUB=	VERSION="${PORTVERSION}"

USES=		gmake
USE_GITHUB=	yes
GH_ACCOUNT=	doxtop
GH_PROJECT=	mimetypes
GH_COMMIT=	0800544
GH_TAGNAME=	${PORTVERSION}

PORTDOCS=	*

.include <bsd.port.options.mk>

do-build:
	cd ${WRKSRC} && rebar compile

do-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/mimetypes-${PORTVERSION}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/mimetypes-${PORTVERSION}/ebin
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/mimetypes-${PORTVERSION}/priv
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/mimetypes-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/ebin/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/mimetypes-${PORTVERSION}/ebin
	${INSTALL_DATA} ${WRKSRC}/priv/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/mimetypes-${PORTVERSION}/priv
	${INSTALL_DATA} ${WRKSRC}/src/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/mimetypes-${PORTVERSION}/src

.include <bsd.port.mk>
