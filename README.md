# win32ports

a collection of ports of various popular, but non-standard headers.

current ports:

- [sys/wait.h](https://github.com/win32ports/sys_wait_h)
- [strings.h](https://github.com/win32ports/strings_h)

requirements for ports:

1. header-only. to avoid integration challenges, and fighting with various build systems, it's much more convinient to provide header-only implementation, which could be just dropped into the project.

2. self-contained. avoid dependencies on other non-standard headers. avoid dependencies on Windows-specific headers (e.g. "windows.h" and friends).

3. written in C. the most specific use-case for these ports is to be used in ports of GNU software (e.g. bison) and other projects written in pure C. therefore, headers cannot use C++. also, they should use standard C, without any GNU extentions, without Microsoft extentions, without C11 and other non-standard staff.

4. portable. although headers are provided only for Windows, they should work in all major compilers, include Visual Studio (at least latest versions, e.g. 2013, 2015, 2017, 2019), GCC (MinGW, both MinGW32 & MinGW64), Clang (clang-cl). others (e.g. Borland, Intel, etc.) aren't currently supported, but patches are always welcomed.

5. tested. write at least some simple unit-tests (at least using assert), use CI to verify it compiles and passes tests.

6. compliant. if header is standardized somehow (e.g. by POSIX), try to follow the standard. try to follow other documentation, if provided, for instance, man pages from Linux, BSD, Solaris, IRIX, AIX, HP-UX, QNX, etc.
