include $(top_srcdir)/config/utility.am

initddir = @SIPX_SERVICEDIR@
initd_SCRIPTS = \
    sipxproxy

EXTRA_DIST = \
	$(initd_SCRIPTS:=.in) \
	$(systemd_SCRIPTS:=.in)
	
systemddir = /usr/lib/systemd/system
systemd_SCRIPTS = \
	sipxproxy.service

$(initd_SCRIPTS) $(systemd_SCRIPTS) : % : %.in Makefile
	@$(call SearchAndReplace,$<,$@)

CLEANFILES = $(initd_SCRIPTS) $(systemd_SCRIPTS)
