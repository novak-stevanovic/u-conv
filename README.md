# UConv

__UConv__ is a tiny C library for converting between UTF-8 and UTF-32 text. It provides functions to decode a byte sequence into Unicode code points and to encode code points back into UTF-8. It is designed with three things in mind: control, proper error handling and simplicity.

## Makefile instructions:

1. `make [LIB_TYPE=so/ar] [OPT={0...3}]` - This will compile the source files(and thirdparty dependencies, if they exist) and build the library file.
2. `make install [PREFIX={prefix}] [LIB_TYPE=so/ar] [PC_PREFIX={pc_prefix}]` - This will place the public headers inside _{prefix}/include_ and the built library file inside _{prefix}/lib_.

Default options are `PREFIX=/usr/local`, `OPT=2`, `LIB_TYPE=so`, `PC_PREFIX=/usr/local/lib/pkgconfig`.

## Usage instructions:

To use the library in your project, you must first install it. This can be done on your system - globally, or locally, inside a project that is using this library.
1. After installing globally, make sure that pkg-config searches inside `PC_PREFIX`. You can do this by appending `PC_PREFIX` to env variable `PKG_CONFIG_PATH`. Then, compile your project with flags: `$(pkgconf --cflags uconv)` and link with flags: `$(pkgconf --libs uconv)`.
2. To install locally, adjust `PREFIX` and `PC_PREFIX` to local directories. Run `make install`. Then, again, make sure that pkg-config searches inside `PC_PREFIX`. You can achieve this by using `--with-path` pkg-config flag or temporarily changing `PKG_CONFIG_PATH`. Again, let pkg-config provide the compilation and linking flags.

Since this "library" consists of a single header and implementation file, you can also just copy and paste it into your project.
