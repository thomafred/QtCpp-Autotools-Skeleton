moc_%.cc: %.h
	@MOC@ -o$@ $(DEFS) $(DEFAULT_INCLUDES) $(INCLUDES) $(AM_CPPFLAGS) $(CPPFLAGS) $(MOC_CPPFLAGS) $<

ui_%.h: %.ui
	@UIC@ -o $@ $<

qrc_%.cc: %.qrc
	@RCC@ -o $@ $<

bin_PROGRAMS = qthello

BUILT_SOURCES = \
    ui_mainwidget.h

qthello_CPPFLAGS = -I$(builddir)

qthello_SOURCES = \
    moc_mainwidget.cc \
    main.cc \
    mainwidget.cc
