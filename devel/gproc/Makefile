# $FreeBSD$

PORTNAME=	gproc
PORTVERSION=	0.2.17
CATEGORIES=	devel

MAINTAINER=	undefined
COMMENT=	Extended process registry for Erlang

BUILD_DEPENDS=	erlc:${PORTSDIR}/lang/erlang \
		rebar:${PORTSDIR}/devel/rebar
RUN_DEPENDS=	erl:${PORTSDIR}/lang/erlang \
		edown>0:${PORTSDIR}/textproc/edown \
		gen_leader>0:${PORTSDIR}/devel/gen_leader

PLIST_SUB=	VERSION="${PORTVERSION}"

USES=		gmake
USE_GITHUB=	yes
GH_ACCOUNT=	uwiger
GH_PROJECT=	gproc
GH_COMMIT=	d66e510
GH_TAGNAME=	${PORTVERSION}

PORTDOCS=	*

.include <bsd.port.options.mk>

post-patch:
	@${REINPLACE_CMD} -e 's|vsn, git|vsn, "${PORTVERSION}"|g' ${WRKSRC}/src/gproc.app.src

#do-build:
#	cd ${WRKSRC} && rebar compile

do-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/gproc-${PORTVERSION}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/gproc-${PORTVERSION}/ebin
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/gproc-${PORTVERSION}/priv
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/gproc-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/ebin/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/gproc-${PORTVERSION}/ebin
	${INSTALL_DATA} ${WRKSRC}/priv/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/gproc-${PORTVERSION}/priv
	${INSTALL_DATA} ${WRKSRC}/src/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/gproc-${PORTVERSION}/src

.include <bsd.port.mk>
