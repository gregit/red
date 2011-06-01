Red Programming Language
------------------------

**Red** is a new programming language strongly inspired by [REBOL](http://rebol.com), but with a broader field of usage thanks to its native-code compiler, from system programming to high-level scripting, while providing a modern support for concurrency and multi-core CPU.

The language is in its early bootstrapping phase. The **Red/System** low-level DSL is the first focus. It is a limited C-level language with a REBOL look'n feel, required to build Red's runtime library. More information on [red-lang.org](http://www.red-lang.org).

Running the Hello script
------------------------
The compiler and linker are currently written in REBOL and produce PE (Windows) or ELF (Linux) executables. So, for now, a REBOL/View binary is required to run it. Follow the instructions:

1. Download a REBOL interpreter suitable for your OS: [Windows](http://www.rebol.com/downloads/v278/rebol-view-278-3-1.exe), [Linux](http://www.rebol.com/downloads/v278/rebol-view-278-4-2.tar.gz)

1. Save it in red-system/ folder and run it, you'll see a `>>` prompt appear

1. Type: `do/args %rsc.r "%tests/hello.reds"`

1. The resulting binary is in red-system/builds/. Windows users need to open a DOS console and run hello.exe from there.

The %rsc.r script is only a wrapper script around the compiler, for testing purpose. It accepts a -v[vvv] option for verbose logs. Try it with:

    >> do/args %rsc.r "-vvvv %tests/hello.reds"

Cross-compilation support
-------------------------
From Windows, to emit Linux executables:

    >> do/args %rsc.r "-f ELF %tests/hello.reds"	

From Linux, to emit Windows executables:

    >> do/args %rsc.r "-f PE %tests/hello.reds"	
