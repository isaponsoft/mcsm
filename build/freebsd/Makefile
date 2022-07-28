PREFIX?=/usr/local
INSTALLDIR=$(DESTDIR)$(PREFIX)

all:
	@echo $(WRKDIRPREFIX)
	@echo $(DISTDIR)


mcsm:
	sed s:MCSM_PREFIX:${INSTALLDIR}/bin: mcsm.rc > mcsm

install: mcsm
	$(INSTALL) ../../bin/mcsm ${INSTALLDIR}/bin
	$(INSTALL) ../../etc/mcsm.conf.default ${INSTALLDIR}/etc
	$(INSTALL) mcsm ${INSTALLDIR}/etc/rc.d
	cp ../../etc/mcsm.conf.default ${INSTALLDIR}/etc/mcsm.conf

clean:
	@-rm mcsm

#	$(INSTALL)

