# Toolchain Windows Build

Pre-build binaries for Windows.

## otfcc

Source: https://github.com/nowar-fonts/otfcc

Commit: 4c4f7993024068bcab672471cc7563e3998d3ad4 (2019-07-29)

Build environment:
+ Windows 10 19H1
+ MSYS2 MinGW
+ MSYS2’s MinGW GCC 9.2.0

## GNU Make (POSIX)

Homepage: https://www.gnu.org/software/make/

Version: 4.2.1

Build environment:
+ Windows 10 19H1
+ MSYS2 MSYS
+ MSYS2’s GCC 9.1.0

`make.exe` depends on `msys-2.0.dll`. The bundled version in Git Bash shall work.

### Why not native build?

It’s buggy.

Consider a Makefile:
```Makefile
all:
	echo hello | sed 's/hello/\\\\/'
```

Native build (running in Git Bash or MSYS2 bash) will perform this result:
```
echo hello | sed 's/hello/\\\\/'
\
```

While POSIX build (this one, MSYS2’s, or Linux distributions’) will perform:
```
echo hello | sed 's/hello/\\\\/'
\\
```
