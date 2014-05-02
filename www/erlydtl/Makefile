# $FreeBSD$

PORTNAME=	erlydtl
PORTVERSION=	0.8.2
CATEGORIES=	www

MAINTAINER=	undefined
COMMENT=	Django templates for Erlang

BUILD_DEPENDS=	erlc:${PORTSDIR}/lang/erlang
RUN_DEPENDS=	erl:${PORTSDIR}/lang/erlang

PLIST_SUB=	VERSION="${PORTVERSION}"

USES=		gmake
USE_GITHUB=	yes
GH_ACCOUNT=	erlydtl
GH_PROJECT=	erlydtl
GH_COMMIT=	26cb8fc
GH_TAGNAME=	${PORTVERSION}

PORTDOCS=	*

.include <bsd.port.options.mk>

do-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}/ebin
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}/include
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}/src
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}/src/filter_lib
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}/src/i18n
	${INSTALL_DATA} ${WRKSRC}/ebin/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}/ebin
	${INSTALL_DATA} ${WRKSRC}/include/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}/include
	${INSTALL_DATA} ${WRKSRC}/src/*.erl ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/src/*.src ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/src/*.yrl ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/src/*.slex ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/src/filter_lib/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}/src/filter_lib
	${INSTALL_DATA} ${WRKSRC}/src/i18n/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/erlydtl-${PORTVERSION}/src/i18n

.include <bsd.port.mk>
