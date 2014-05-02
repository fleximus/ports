# $FreeBSD$

PORTNAME=	gen_leader
PORTVERSION=	0.1
CATEGORIES=	devel

MAINTAINER=	undefined
COMMENT=	Project to unify various implementations of the Erlang library gen_leader into a modern, robust single implementation

BUILD_DEPENDS=	erlc:${PORTSDIR}/lang/erlang \
		rebar:${PORTSDIR}/devel/rebar
RUN_DEPENDS=	erl:${PORTSDIR}/lang/erlang

PLIST_SUB=	VERSION="${PORTVERSION}"

USES=		gmake
USE_GITHUB=	yes
GH_ACCOUNT=	abecciu
GH_PROJECT=	gen_leader_revival
GH_COMMIT=	a119cb9
GH_TAGNAME=	a119cb9a39

PORTDOCS=	*

.include <bsd.port.options.mk>

do-build:
	cd ${WRKSRC} && rebar compile

do-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/gen_leader-${PORTVERSION}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/gen_leader-${PORTVERSION}/ebin
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/gen_leader-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/ebin/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/gen_leader-${PORTVERSION}/ebin
	${INSTALL_DATA} ${WRKSRC}/src/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/gen_leader-${PORTVERSION}/src

.include <bsd.port.mk>
