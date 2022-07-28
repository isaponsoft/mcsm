PREFIX?=/usr/local
INSTALLDIR=$(DESTDIR)$(PREFIX)
VERSION=0.0.1
TARBALL=mcsm-${VERSION}.tar.gz
TMPDIR?=/tmp
WORKDIR=${TMPDIR}/mcsm


all: mcsm


mcsm:
	sed s:MCSM_PREFIX:${INSTALLDIR}/bin: mcsm.rc > mcsm

install:
	$(INSTALL) ../../bin/mcsm ${INSTALLDIR}/bin
	$(INSTALL) ../../etc/mcsm.conf.default ${INSTALLDIR}/etc
	$(INSTALL) mcsm ${INSTALLDIR}/etc/rc.d

clean:
	@-rm mcsm

# create ports tarball.
ports-build:
	-rm -fr ${WORKDIR}/*
	mkdir -p ${WORKDIR}
	cp -rp ../../ ${WORKDIR}/mcsm-${VERSION}
	cd ${WORKDIR} && tar czv -X mcsm-${VERSION}/build/tar-exclude.list -f ${TARBALL} mcsm-${VERSION}
	cp ${WORKDIR}/${TARBALL} ports/.
	cp ${WORKDIR}/${TARBALL} ${DISTDIR}
	cd ports && make makesum

# ports test.
ports-test: ports-build
	cd ports && rm -fr ${WRKDIRPREFIX}$(PWD)
	cd ports && make clean stage stage-qa deinstall
	cd ports && make install
	cd ports && make package
	cd ports && make reinstall

	