dnl Process this file with autoconf to produce a configure script.

AC_PREREQ(2.59)
AC_INIT([gnuTroll], [1.0])

AC_CONFIG_MACRO_DIR([m4])

AC_CONFIG_AUX_DIR([bin])

PKG_PROG_PKG_CONFIG

AC_CANONICAL_SYSTEM
AM_INIT_AUTOMAKE([-Wall foreign 1.9.6])
AM_SILENT_RULES

AM_PROG_CC_C_O
AC_PROG_CXX
AM_PROG_AR
AC_PROG_LIBTOOL

# Configure pthreads.
ACX_PTHREAD([have_pthread=yes])

AC_HEADER_STDC
AC_CHECK_HEADERS([stdlib.h])

# Configure Doxygen
# DX_HTML_FEATURE(ON)
# DX_CHM_FEATURE(OFF)
# DX_CHI_FEATURE(OFF)
# DX_MAN_FEATURE(OFF)
# DX_RTF_FEATURE(OFF)
# DX_XML_FEATURE(OFF)
# DX_PDF_FEATURE(ON)
# DX_PS_FEATURE(OFF)

#DX_INIT_DOXYGEN([$PACKAGE_NAME],[src/doxygen.cfg])

# Check for Qt Libraries
PKG_CHECK_MODULES(QT, [QtCore, QtGui, QtNetwork], [], [AC_MSG_ERROR([Qt libraries required.])])

# Retrieve Qt compilation and linker flags
CPPFLAGS="`$PKG_CONFIG --cflags-only-I QtCore QtGui QtNetwork` $CPPFLAGS"
LDFLAGS="`$PKG_CONFIG --libs-only-L QtCore QtGui QtNetwork` $LDFLAGS"
LIBS="`$PKG_CONFIG --libs-only-l QtCore QtGui QtNetwork` $LIBS"

if !'$PKG_CONFIG --atleast-version=5.0.0 QtCore'; then
  AC_MSG_ERROR([Qt >= 5.0.0 is required.])
fi

AC_CHECK_PROGS(MOC, [moc-qt5 moc])
AC_CHECK_PROGS(UIC, [uic-qt5 uic])
AC_CHECK_PROGS(RCC, [rcc])

if test -z "$MOC" || test -z "$UIC" || test -z "$RCC"; then
  AC_MSG_ERROR([Qt utility programs moc, uic, and rcc are required.])
fi


AC_FUNC_MALLOC
AC_CONFIG_HEADERS([config.h])

AC_CONFIG_FILES([ 
          Makefile 
          src/Makefile
          src/lib/libname/Makefile
          src/app/Makefile
          bindings/Makefile
          examples/Makefile
          tests/Makefile
          tests/unitTests/Makefile
])
		  

AC_OUTPUT

AC_MSG_RESULT([
Configure Information:
  Preprocessor      :
    CPPFLAGS        : $CPPFLAGS

  C Compiler        : $CC
    DEFS            :   $DEFS
    CFLAGS          :   $CFLAGS
    
  C++ Compiler      : $CXX
    CXXFLAGS        :   $CXXFLAGS

  Linker            : $LD
    LDFLAGS         :   $LDFLAGS
    LIBS            :   $LIBS

 ])
