
                             Lynx 2.8 for OS/2
                                      
Table of Contents

     * [1]Introduction
     * [2]What's new?
     * [3]Installation from binary distribution
     * [4]Installation from source distribution
     * [5]Getting Help
     * [6]Bugs
     * [7]License
       
Introduction

   Hello and welcome to Lynx 2.8 for OS/2. This is a port of Lynx 2.8
   from the Lynx-Dev sources. Be sure to read the included [8]README
   file, which is more general than this file, which applies only to the
   OS/2 port.
   
Why Lynx?

   Lynx is a full featured text-oriented browser for the World Wide Web.
   Though the trend in recent years has been towards graphical browsers,
   there are still many good reasons for using Lynx. Lynx can be used to
   format WWW output for users with special needs, such as the visually
   impaired. Lynx is also much faster than any other browser out there,
   and is good for doing quick lookups on URLs from a newsreader, for
   example. Lynx lets you cut through the style and get right to the
   substance.
   
What's New?

   Lots!
   
   Here are some of the major chages since Lynx 2.7.1. The changes since
   Lynx 2.4, which Lynx/2 was based on are too many to name.
     * New Sorta-SGML parser (^V to toggle between new and old parser)
     * Ncurses color-support (works in OS/2 window or xterm). Two ways of
       selecting colors: color for types of emphasis in lynx.cfg (what
       used to be bold can now be red, for example), or experimental
       color-styles allow you to set color for any HTML element using a
       stylesheet.
     * External commands: use wget or ncftp to do external downloads
       while you keep browsing in Lynx. Or start up a new Lynx window
       from a hyperlink within Lynx!
     * Experimental partial display code lets you see long pages as they
       download.
     * Lots of small interface tweaks and bug fixes.
     * In 2.8.1 and later, OS/2-EMX will be a supported platform for
       Lynx; no need to patch sources to recompile.
       
Installation

Hardware and Software Requirements

   Hardware
     * An IBM-compatible PC capable of running OS/2 2.1 or later with
       TCP/IP
     * In effect, a 386sx or better with at least 8 MB of RAM.
       
   Software
   
     * OS/2 2.1 or later (I think...should definitely be OK on Warp 3 or
       later).
     * An HPFS partition, as I haven't made any allowances for FAT
       filenames. Actually, FAT might work, but you won't have any online
       help.
     * IBM TCP/IP 2.0 or later (?) Warp 3 IAK, Warp Connect, and Warp 4
       all fit the bill.
     * EMX runtime 0.9c or later.
     * GNU File Utilities. You need at least 'cp', and I'm not sure what
       all else.
       
  Installation Procedure
  
   This is probably a little harder than it needs to be right now. I'll
   try to make it as straightforward as possible.
    1. Unzip the Lynx 2.8 package into a directory. You've probably
       already done this.
    2. If you haven't installed the EMX runtime or the GNU file utils,
       now is a good time. If you don't have the GNU Fileutils and don't
       want to install them, copy the file lcp.exe to cp.exe in the same
       directory as your lynx.exe.
    3. Copy lynx-std.exe and/or lynx-sty.exe to somewhere on your path,
       or to its own directory. Put lynx.cfg somewhere;if lynx has its
       own directory you may want to put it there. This build of Lynx
       will look in the %HOME% directory (the directory specified by the
       HOME environment variable) for both lynx.cfg and lynx.lss.
       Lynx.lss should go in %HOME%. You need to put the helpfiles
       somewhere, too. If lynx has its own directory, put their
       directories under it.
    4. Move the terminfo directory somewhere. Lynx will look for terminfo
       files either in %TERMINFO% or in %HOME%/.terminfo. Lynx will also
       use TERMCAP if it can't find the terminfo files; if you use
       termcap, color won't work.
    5. Set some environment variables in your config.sys:
          + set HOME=x:/pathname (where you want personal configuration
            files, signature files, etc to go)
          + set TMP=x:/tmpspace (a temporary directory)
          + set TERMINFO=x:/terminfo_path (where you moved the terminfo
            directory, e.g. set TERMINFO=d:/emx/terminfo.)
          + set TERM=something (where something is a terminal type
            supported by terminfo and hopefully also termcaps: "ansi" is
            a reasonable if unaesthetic value.)
          + set WWW_HOME=scheme://some.random.url/ (the URL you want Lynx
            to load on startup. For example, set
            WWW_HOME=http://www.ibm.com/.)
          + set LYNX_CONFIG=x:/pathname/lynx.cfg (Path where you put
            lynx.cfg; if lynx.cfg is in %HOME% you don't have to set
            this.).
    6. Edit your lynx.cfg file to suit your needs. Some things in here
       must be changed to suit your configuration (especially your
       domain, and the location to helpfiles, etc.).
    7. Reboot to activate your environment variables; make a desktop
       object for Lynx if you wish. Alternatively, instead of modifying
       config.sys and rebooting, you can make a lynx.cmd file containing
       all of the environment variable settings and running Lynx.
    8. Happy Lynxing!
       
   There are two Lynx executables included in this package. Lynx-std.exe
   is built to use the standard method of color selection; look in
   lynx.cfg for the COLOR directives and associated comments.
   Lynx-sty.exe is built to use color styles for color selection; edit
   lynx.lss to set colors for particular HTML elements. The two methods
   have their own strengths and weaknesses. The color-styles version
   gives you finer control over what colors are used for what kinds of
   text, but you can't really set the main/default background color with
   it. It is also hard to predict exactly what results you will get when
   various HTML tags are combined! The color-styles code is experimental.
   The standard method lets you use fewer colors, but it lets you set the
   overall background color, for example. In my experience, the standard
   method is better in OS/2 windowed or full-screen sessions, while the
   color-styles method is better in an xterm. In fact, it looks [9]really
   good in rxvt.
   
Installation from sources.

   In order to compile Lynx for OS/2, you need a number of different
   packages. You can get either the OS/2-specific source distribution
   (from Hobbes or probably whereever you got this package), or get the
   latest sources from [10]the Lynx experimental distribution directory.
   You will need the EMX/GCC compiler, [11]Autoconf for OS/2 and
   [12]Ncurses for OS/2. Unpack the Lynx source. Use autoconf to rebuild
   the configure script (this will require an extremely complete set of
   unix-like utilities for OS/2). Run configure, and edit the resulting
   lynx_cfg.h to your satisfaction. Most things will be fine, but make
   sure that the names of programs (cp, gzip, etc) are correct; that's
   the only thing configure is likely to get wrong. Run 'make', and
   everything should go perfectly smoothly.
   
Getting Help

   The best place to start looking for help is in the Lynx help files. If
   you have Lynx set up correctly, you can browse them just by hitting
   'h' or '?'. If not, try looking at them with WebExplorer.
   
   Lots of good information is available from [13]Lynx Links. I may have
   more specific information about Lynx for OS/2 available from my
   [14]Lynx page. If you're totally stuck, you can [15]email me, but
   please don't send me any general Lynx questions, etc; just problems,
   suggestions, or compliments regarding the OS/2 port.
   
Bugs

   These are the bugs I know about:
     * Basic dired support works, but many features don't work: you can't
       move or change the permissions on files.
     * There are some glitches in the display with the standard method of
       color selection. If the screen gets missed up and ^L doesn't clear
       it up, try typing v (for the bookmarks page) and ^G to cancel. I
       think it's an ncurses problem; maybe just the terminfo files.
       There are also some display problems in an xterm; use TERM=x10term
       or TERM=rxvt to get around it.
       
   If anyone finds any other bugs, [16]let me know. In particular, I may
   well have missed any number of places where Unix-like pathnames are
   expected.
   
License

   Lynx is distributed under the [17]GNU Public License, which you should
   read. There is no warranty, as described in the license agreement.
     _________________________________________________________________
   
   
    Jason.McBrayer@Tulane.edu
    
   Last modified: Tue Jun 23 18:57:32 -0600 1998

References

   1. file://localhost/./readme_os2.html#intro
   2. file://localhost/./readme_os2.html#new
   3. file://localhost/./readme_os2.html#install
   4. file://localhost/./readme_os2.html#compile
   5. file://localhost/./readme_os2.html#help
   6. file://localhost/./readme_os2.html#bugs
   7. file://localhost/./readme_os2.html#license
   8. file://localhost/./README
   9. file://localhost/./lynx-style.gif
  10. http://sol.slcc.edu/lynx/current/
  11. http://www.arrakis.es/acemx.htm
  12. http://www.arrakis.es/ncemx.htm
  13. http://www.crl.com/~subir/lynx.html
  14. http://studentweb.tulane.edu/~jmcbray/lynx
  15. mailto:Jason.McBrayer@tulane.edu
  16. mailto:Jason.McBrayer@tulane.edu
  17. file://localhost/./COPYING
