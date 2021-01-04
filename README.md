[![Galaxy](https://img.shields.io/badge/galaxy-dockpack.base__cplusplus-blue.svg?style=flat)](https://galaxy.ansible.com/dockpack/base_cplusplus)[![Build Status](https://api.travis-ci.org/dockpack/base_cplusplus.svg)](https://travis-ci.org/dockpack/base_cplusplus)

base_boost is an ansible-role that installs libraries for GNU C++ compiler tools

Requirements
------------

RHEL-like system, or Ubuntu, or Windows.


Role Variables
--------------
- Corporate feature: toggles desired state
`compilers_present: present`

- Software collections offer latest versions of programming languages
`collections_enabled: true`

- approved/test release of software collections' devtoolset
`cplusplus_devtoolset: devtoolset-7`

Most Boost libraries are header-only: they consist entirely of header files containing templates and inline functions, and require no separately-compiled library binaries or special treatment when linking. Yet this role does compile libraries, but you can override that behaviour if you like:

```
compile_boost: true
```
The only Boost libraries that must be built separately, and have no extra documentation to compile, are set as default (override them in group_vars or your playbook):

```
compile_boost_with:
  --with-chrono
  --with-context
  --with-filesystem
  --with-graph_parallel
  --with-iostreams
  --with-locale
  --with-program_options
  --with-regex
  --with-serialization
  --with-signals
  --with-system
  --with-thread
  --with-timer
  --with-wave
```



# # boost_cflags valuse for windows

    /DFOO - define FOO in the preprocessor
    /EHsc - catch C++ exceptions, assume extern "C" functions never throw C++ exceptions
    /GR - enable RTTI
    /MD - make a multithreaded DLL
    /MDd - make a debug multithreaded DLL
    /O1 - optimize for size
    /O2 - optimize for speed
    /Ob0 - no auto-inlining
    /Ob1 - only inline functions that are marked inline, and C++ member functions defined in a class declaration
    /Ob2 - let compiler inline freely
    /Od - no optimization
    /RTC1 - run-time checking: report when a variable is used without being initialized, and stack frame run-time error checking. See their site for more details.
    /W3 - use warning level 3 (out of 4), “production quality”
    /Zi - generate “complete debugging information”, like -g for clang/gcc



Dependencies
------------

https://www.softwarecollections.org/en/docs/

Example Usage
----------------

Refer to a complete build server https://github.com/bbaassssiiee/buildserver

License
-------

MIT

Author Information
------------------

Bas Meijer
@bbaassssiiee
