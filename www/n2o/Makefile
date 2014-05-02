# $FreeBSD: www/n2o/Makefile 333103 2013-11-07 14:33:57Z olgeni $

PORTNAME=	n2o
PORTVERSION=	0.11.0
CATEGORIES=	www

MAINTAINER=	undefined
COMMENT=	Erlang Web Framework on WebSockets

BUILD_DEPENDS=	erlc:${PORTSDIR}/lang/erlang
RUN_DEPENDS=	erl:${PORTSDIR}/lang/erlang \
		cowboy>=0:${PORTSDIR}/www/cowboy

PLIST_SUB=	VERSION="${PORTVERSION}"

USES=		gmake
USE_GITHUB=	yes
GH_ACCOUNT=	5HT
GH_PROJECT=	n2o
GH_COMMIT=	b4c61fb
GH_TAGNAME=	${PORTVERSION}

PORTDOCS=	*

.include <bsd.port.options.mk>

post-patch:
	${LN} -sf ${WRKSRC} ${WRKDIR}/n2o

do-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
#	${INSTALL_DATA} ${WRKSRC}/doc/* ${STAGEDIR}${DOCSDIR}
	@${MKDIR} ${STAGEDIR}${EXAMPLESDIR}
	cd ${WRKSRC}/samples && ${COPYTREE_SHARE} . ${STAGEDIR}${EXAMPLESDIR}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/n2o-${PORTVERSION}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/n2o-${PORTVERSION}/ebin
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/n2o-${PORTVERSION}/priv
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/erlang/lib/n2o-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/ebin/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/n2o-${PORTVERSION}/ebin
	${INSTALL_DATA} ${WRKSRC}/priv/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/n2o-${PORTVERSION}/priv
	${INSTALL_DATA} ${WRKSRC}/src/* ${STAGEDIR}${PREFIX}/lib/erlang/lib/n2o-${PORTVERSION}/src

.include <bsd.port.mk>
