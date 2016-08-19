ActionScript 3.0 Conversion Guide

\#\# Overview

In 2001, the popularity of Flash and ActionScript continued to grow as artists and developers discovered the infinite possibilities of an expressive web platform.

Unfortunately, the only method available for compiling Actionscript was to use the Macromedia Flash editor, or to use Macromedia's server-side Generator product. There were no free ActionScript compilers, particularly open-source ones, until Nicolas Cannasse and Motion-Twin created MTASC, the "Motion Twin ActionScript Compiler"

Tools like MTASC, swfmill and other open-souce Flash resources grew in popularity. Fast-forward in time, Macromedia began releasing alpha previews of ActionScript 3.0 and the new ActionScript virtual machine \\(AVM2\\). This time, Macromedia did promise a free compiler \\(in the form of the Flex SDK\\). Rather than create a redundant solution for compiling ActionScript 3.0, Nicolas instead worked on a new programming language, inspired by ActionScript, but designed from day one to cross-compile to multiple target runtimes. Haxe was created, generating AVM2 bytecode directly \\(similar to ActionScript 3.0\\) but also compatible with JavaScript and PHP for client- and server-side programming.

Today, Haxe has grown to support more than ten output targets, including mature support for C++ and broad support for Java or C\\#, and is used successfully in many projects from embedded set-top boxes to the mobile web, desktop games and game console development. Haxe continues to get better, and with the explosion of devices since Flash was first created, the need and power of a cross-target solution becomes all the more essential.

\#\# Declining Browser Support

Browser support for the Flash Player plugin has been in decline since smartphones increased in popularity. What was possible only through a plugin is now largely possible through the web browser, so there has been a steady increase in pressure to discontinue support for the Netscape plugin architecture \\(NPAPI\\) in favor of browser-based solutions.

Flash has received a lot of negative press that fundamentally comes down to declining browser plugin support. The Unity Web Player, for example, has been subject to the same pressure.

\#\# Flash, not Flash Player

"Flash" and "Flash Player" are inseparable terms for many people, but the open-source community makes the argument that these can be completely separate.

Without Flash Player, there is no ActionScript virtual machine. Especially in the web browser, choices are limited to V8, SpiderMonkey, Chakra or another JavaScript virtual machine. In Haxe, AVM2 and JavaScript are both fully supported. Using OpenFL, an open implementation of Flash APIs, it is possible to develop "Flash" content without using Flash Player at all.

Beyond the browser, Flash Player is available in the form of Adobe AIR for desktop and mobile, but there are still limitations that prevent developers from creating Linux native applications, releasing for console platforms, or integrating with deeper features than are provided. OpenFL also includes support for native desktop and mobile publishing, and unofficially has been used in embedded devices, console platforms and single-board computers \\(such as the Raspberry Pi\\).

