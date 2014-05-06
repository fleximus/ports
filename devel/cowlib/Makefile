# $FreeBSD$

PORTNAME=	cowlib
PORTVERSION=	0.6.1
CATEGORIES=	www

MAINTAINER=	undefined
COMMENT=	Support library for manipulating Web protocols

BUILD_DEPENDS=	erlc:${PORTSDIR}/lang/erlang
RUN_DEPENDS=	erl:${PORTSDIR}/lang/erlang

PLIST_SUB=	VERSION="${PORTVERSION}"

USES=		gmake
USE_GITHUB=	yes
GH_ACCOUNT=	extend
GH_PROJECT=	cowlib
GH_COMMIT=	f58340a
GH_TAGNAME=	${PORTVERSION}

.include <bsd.port.options.mk>

do-install:
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/cowlib-${PORTVERSION}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/cowlib-${PORTVERSION}/ebin
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/cowlib-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/ebin/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/cowlib-${PORTVERSION}/ebin
	${INSTALL_DATA} ${WRKSRC}/src/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/cowlib-${PORTVERSION}/src

.include <bsd.port.mk>
