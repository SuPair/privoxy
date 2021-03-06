cmake_minimum_required(VERSION 3.8)
project(privoxy_3_0_26_stable)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_VERBOSE_MAKEFILE ON)
if (MINGW)
    set(CMAKE_EXE_LINKER_FLAGS "-mwindows")
    set(CMAKE_EXE_LINKER_FLAGS_RELEASE "-s")
    link_libraries("wsock32" "comctl32" "pcre")
endif ()

set(SOURCE_FILES
        pcre/chartables.c
        pcre/config.h
        #        pcre/dftables.c
        pcre/get.c
        pcre/internal.h
        pcre/maketables.c
        pcre/pcre.c
        pcre/pcre.h
        #        pcre/pcregrep.c
        pcre/pcreposix.c
        pcre/pcreposix.h
        #        pcre/pcretest.c
        pcre/study.c
        acconfig.h
        actionlist.h
        actions.c
        actions.h
        amiga.c
        amiga.h
        cgi.c
        cgi.h
        cgiedit.c
        cgiedit.h
        cgisimple.c
        cgisimple.h
        client-tags.c
        client-tags.h
        cygwin.h
        deanimate.c
        deanimate.h
        encode.c
        encode.h
        errlog.c
        errlog.h
        filters.c
        filters.h
        gateway.c
        gateway.h
        jbsockets.c
        jbsockets.h
        jcc.c
        jcc.h
        list.c
        list.h
        loadcfg.c
        loadcfg.h
        loaders.c
        loaders.h
        miscutil.c
        miscutil.h
        parsers.c
        parsers.h
        pcrs.c
        pcrs.h
        project.h
        ssplit.c
        ssplit.h
        strptime.h
        urlmatch.c
        urlmatch.h
        w32log.c
        w32log.h
        w32res.h
        w32svrapi.c
        w32svrapi.h
        w32taskbar.c
        w32taskbar.h
        win32.c
        win32.h)

set(DFTABLES_SOURCE_FILES
        pcre/chartables.c
        pcre/config.h
        pcre/dftables.c
        pcre/get.c
        pcre/internal.h
        pcre/maketables.c
        pcre/pcre.c
        pcre/pcre.h
        #        pcre/pcregrep.c
        pcre/pcreposix.c
        pcre/pcreposix.h
        #        pcre/pcretest.c
        pcre/study.c)

set(PCREGREP_SOURCE_FILES
        pcre/chartables.c
        pcre/config.h
        #                pcre/dftables.c
        pcre/get.c
        pcre/internal.h
        pcre/maketables.c
        pcre/pcre.c
        pcre/pcre.h
        pcre/pcregrep.c
        pcre/pcreposix.c
        pcre/pcreposix.h
        #        pcre/pcretest.c
        pcre/study.c)

set(PCRETEST_SOURCE_FILES
        pcre/chartables.c
        pcre/config.h
        #                pcre/dftables.c
        pcre/get.c
        pcre/internal.h 
        pcre/maketables.c
        pcre/pcre.c
        pcre/pcre.h
        #        pcre/pcregrep.c
        pcre/pcreposix.c
        pcre/pcreposix.h
        pcre/pcretest.c
        pcre/study.c)

add_executable(privoxy_3_0_26_stable ${SOURCE_FILES})
add_executable(dftables ${DFTABLES_SOURCE_FILES})
add_executable(pcregrep ${PCREGREP_SOURCE_FILES})
add_executable(pcretest ${PCRETEST_SOURCE_FILES})