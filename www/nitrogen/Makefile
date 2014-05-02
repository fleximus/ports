# $FreeBSD$

PORTNAME=	nitrogen
PORTVERSION=	2.2.2
CATEGORIES=	www

MAINTAINER=	undefined
COMMENT=	Nitrogen Web Framework for Erlang

BUILD_DEPENDS=	erlc:${PORTSDIR}/lang/erlang
RUN_DEPENDS=	erl:${PORTSDIR}/lang/erlang

PLIST_SUB=	VERSION="${PORTVERSION}"

USES=		gmake
USE_GITHUB=	yes
GH_ACCOUNT=	nitrogen
GH_PROJECT=	nitrogen
GH_COMMIT=	ed8aad4
GH_TAGNAME=	v${PORTVERSION}

PORTDOCS=	*

OPTIONS_DEFAULT=	COWBOY
OPTIONS_SINGLE=		WEB
OPTIONS_SINGLE_WEB=	COWBOY MOCHIWEB YAWS

WEB_DESC=		Webserver support
COWBOY_DESC=		Cowboy webserver
MOCHIWEB_DESC=		Mochiweb webserver
YAWS_DESC=		Yaws webserver

.include <bsd.port.options.mk>

.  if ${PORT_OPTIONS:MCOWBOY}
ALL_TARGET=	slim_cowboy
RUN_DEPENDS+=	cowboy>=0:${PORTSDIR}/www/cowboy
.  endif

.  if ${PORT_OPTIONS:MMOCHIWEB}
ALL_TARGET=slim_mochiweb
RUN_DEPENDS+=	mochiweb>=0:${PORTSDIR}/www/mochiweb
.  endif

.  if ${PORT_OPTIONS:MYAWS}
ALL_TARGET=slim_yaws
RUN_DEPENDS+=	yaws>=0:${PORTSDIR}/www/yaws
.  endif


do-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}/ebin
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}/include
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}/src
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}/src/filter_lib
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}/src/i18n
	${INSTALL_DATA} ${WRKSRC}/ebin/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}/ebin
	${INSTALL_DATA} ${WRKSRC}/include/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}/include
	${INSTALL_DATA} ${WRKSRC}/src/*.erl ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/src/*.src ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/src/*.yrl ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/src/*.slex ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/src/filter_lib/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}/src/filter_lib
	${INSTALL_DATA} ${WRKSRC}/src/i18n/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/nitrogen-${PORTVERSION}/src/i18n

.include <bsd.port.mk>
