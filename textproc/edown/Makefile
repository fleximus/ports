# $FreeBSD$

PORTNAME=	edown
PORTVERSION=	0.3.1
CATEGORIES=	devel

MAINTAINER=	undefined
COMMENT=	Erlang EDoc extension for generating Github-flavored Markdown

BUILD_DEPENDS=	erlc:${PORTSDIR}/lang/erlang \
		rebar:${PORTSDIR}/devel/rebar
RUN_DEPENDS=	erl:${PORTSDIR}/lang/erlang

PLIST_SUB=	VERSION="${PORTVERSION}"

USES=		gmake
USE_GITHUB=	yes
GH_ACCOUNT=	esl
GH_PROJECT=	edown
GH_COMMIT=	b89668e
GH_TAGNAME=	${PORTVERSION}

PORTDOCS=	*

.include <bsd.port.options.mk>

post-patch:
	@${REINPLACE_CMD} -e "s|vsn, git|vsn, \"${PORTVERSION}\"|g" ${WRKSRC}/src/edown.app.src

do-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/edown-${PORTVERSION}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/edown-${PORTVERSION}/ebin
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/edown-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/ebin/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/edown-${PORTVERSION}/ebin
	${INSTALL_DATA} ${WRKSRC}/src/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/edown-${PORTVERSION}/src

.include <bsd.port.mk>
