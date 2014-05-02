PORTNAME=	leofs
PORTVERSION=	0.16.8
CATEGORIES=	databases
MASTER_SITES=	GH

MAINTAINER=	undefined
COMMENT=	Unstructured Big Data Storage for the Web

BUILD_DEPENDS=	git:${PORTSDIR}/devel/git \
		cmake:${PORTSDIR}/devel/cmake \
		${LOCALBASE}/lib/libcheck.a:${PORTSDIR}/devel/libcheck \
		erlc:${PORTSDIR}/lang/erlang \
RUN_DEPENDS=	erl:${PORTSDIR}/lang/erlang \
		ranch>=0:${PORTSDIR}/net/ranch \
		cowboy>=0:${PORTSDIR}/www/cowboy

PLIST_SUB=	VERSION="${PORTVERSION}"

USE_GMAKE=	yes
USES=		pkgconfig
MAKE_ENV=	"GIT_SSL_NO_VERIFY=true"
USE_GITHUB=	yes
GH_ACCOUNT=	leo-project
GH_PROJECT=	leofs
GH_COMMIT=	e9b9aa9
GH_TAGNAME=	${PORTVERSION}

PORTDOCS=	*

NO_STAGE=	yes
.include <bsd.port.options.mk>

do-install:
.if ${PORT_OPTIONS:MDOCS}
	@${MKDIR} ${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/guide/* ${DOCSDIR}
.endif
.if ${PORT_OPTIONS:MEXAMPLES}
	@${MKDIR} ${EXAMPLESDIR}
	cd ${WRKSRC}/examples && ${COPYTREE_SHARE} . ${EXAMPLESDIR}
.endif
	@${MKDIR} ${PREFIX}/lib/erlang/lib/leofs-${PORTVERSION}
	@${MKDIR} ${PREFIX}/lib/erlang/lib/leofs-${PORTVERSION}/ebin
	@${MKDIR} ${PREFIX}/lib/erlang/lib/leofs-${PORTVERSION}/src
	${INSTALL_DATA} ${WRKSRC}/ebin/* ${PREFIX}/lib/erlang/lib/leofs-${PORTVERSION}/ebin
	${INSTALL_DATA} ${WRKSRC}/src/* ${PREFIX}/lib/erlang/lib/leofs-${PORTVERSION}/src

.include <bsd.port.mk>
