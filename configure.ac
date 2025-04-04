dnl Process this file with autoconf to produce a configure script.
AC_PREREQ([2.72])
AC_INIT([MHASH],[0.9.9],[mhash-devel@sourceforge.net])
AC_CANONICAL_TARGET
AC_CONFIG_SRCDIR([lib/mhash.c])
AC_CONFIG_MACRO_DIR([m4])
AM_INIT_AUTOMAKE([foreign -Wall])

AC_DEFINE([MHASH_VERSION], PROGRAM_VERSION, "MHash Version")
AC_CONFIG_HEADERS([include/mutils/config.h include/mutils/mhash_config.h])


dnl Check system.

AC_USE_SYSTEM_EXTENSIONS
AC_SEARCH_LIBS([strerror],[cposix])

dnl Checks for programs.

AM_PROG_AS
AC_PROG_CC
AC_PROG_CC_C_O
AC_PROG_CXX
AC_PROG_INSTALL
AC_PROG_LN_S
AM_PROG_AR

dnl Check Make characteristics
AC_PROG_MAKE_SET

dnl Check C characteristics

AC_LANG(C)

AC_C_CONST
AC_C_INLINE
AC_C_PROTOTYPES
AC_C_BIGENDIAN

dnl Miscellaneous checks

AC_C_CONST

LT_INIT([win32-dll])

AC_TYPE_SIZE_T

dnl Checks for headers

AC_HEADER_STDBOOL

AC_CHECK_HEADERS([sys/endian.h sys/stat.h sys/types.h sys/mman.h])
AC_CHECK_HEADERS([assert.h byteswap.h dlfcn.h ctype.h errno.h])
AC_CHECK_HEADERS([endian.h fcntl.h inttypes.h limits.h])
AC_CHECK_HEADERS([malloc.h unistd.h utime.h values.h])
AC_CHECK_HEADERS([signal.h stdint.h stdio.h stdlib.h string.h strings.h])

dnl Checks for functions

AC_FUNC_MALLOC
AC_FUNC_MEMCMP

AC_CHECK_FUNCS(bcopy bzero)
AC_CHECK_FUNCS(fcntl fsync)
AC_CHECK_FUNCS(memset memmove mlock)
AC_CHECK_FUNCS(sigaction signal)
AC_CHECK_FUNCS(readdir_r readdir)
AC_CHECK_FUNCS(strtol)
AC_CHECK_FUNCS(lstat stat)
AC_CHECK_FUNCS(umask utime)

dnl Checks type sizes.

AC_CHECK_SIZEOF(unsigned long long int, 8)
AC_CHECK_SIZEOF(unsigned long int, 4)
AC_CHECK_SIZEOF(unsigned int, 4)
AC_CHECK_SIZEOF(unsigned short int, 2)
AC_CHECK_SIZEOF(unsigned char, 1)

dnl Checks for optional libraries and tools

AM_WITH_DMALLOC

AC_ARG_ENABLE(md5,
[AS_HELP_STRING([--disable-md5],[disable the MD5 algorithm])],,
AC_DEFINE(ENABLE_MD5, 1, "MD-5 Algorithm"))

AC_ARG_ENABLE(sha1,
[AS_HELP_STRING([--disable-sha1],[disable the SHA1 algorithm])],,
AC_DEFINE(ENABLE_SHA1, 1, "SHA-1 Algorithm"))

AC_ARG_ENABLE(md4,
[AS_HELP_STRING([--disable-md4],[disable the MD4 algorithm])],,
AC_DEFINE(ENABLE_MD4, 1, "MD-4 Algorithm"))

AC_ARG_ENABLE(md2,
[AS_HELP_STRING([--disable-md2],[disable the MD2 algorithm])],,
AC_DEFINE(ENABLE_MD2, 1, "MD-2 Algorithm"))

AC_ARG_ENABLE(tiger,
[AS_HELP_STRING([--disable-tiger],[disable the TIGER algorithm])],,
AC_DEFINE(ENABLE_TIGER, 1, "Tiger Algorithm"))

AC_ARG_ENABLE(haval,
[AS_HELP_STRING([--disable-haval],[disable the HAVAL algorithm])],,
AC_DEFINE(ENABLE_HAVAL, 1, "Haval Algorithm"))

AC_ARG_ENABLE(crc32,
[AS_HELP_STRING([--disable-crc32],[disable the CRC32 algorithm])],,
AC_DEFINE(ENABLE_CRC32, 1, "CRC32 Algorithm"))

AC_ARG_ENABLE(adler32,
[AS_HELP_STRING([--disable-adler32],[disable the ADLER32 algorithm])],,
AC_DEFINE(ENABLE_ADLER32, 1, "Adler32 Algorithm"))

AC_ARG_ENABLE(ripemd,
[AS_HELP_STRING([--disable-ripemd],[disable the RIPEMD128/160/256/320 algorithms])],,
AC_DEFINE(ENABLE_RIPEMD, 1, "RIPE-MD - RIPE Substitute for MD"))

AC_ARG_ENABLE(gost,
[AS_HELP_STRING([--disable-gost],[disable the GOST algorithm])],,
AC_DEFINE(ENABLE_GOST, 1, "GOST Algorithm"))

AC_ARG_ENABLE(sha256-sha224,
[AS_HELP_STRING([--disable-sha256-sha224],[disable the SHA256 and SHA224 algorithms])],,
AC_DEFINE(ENABLE_SHA256_SHA224, 1, "SHA-224 and SHA-256 - SHA-2 Algorithms"))

AC_ARG_ENABLE(sha512-sha384,
[AS_HELP_STRING([--disable-sha512-sha384],[disable the SHA512 and SHA384 algorithms])],,
AC_DEFINE(ENABLE_SHA512_SHA384, 1, "SHA-384 and SHA-512 - SHA-2 Algorithms"))

AC_ARG_ENABLE(snefru,
[AS_HELP_STRING([--disable-snefru],[disable the SNEFRU algorithm])],,
AC_DEFINE(ENABLE_SNEFRU, 1, "Snefru Algorithm"))

AC_ARG_ENABLE(whirlpool,
[AS_HELP_STRING([--disable-whirlpool],[disable the WHIRLPOOL algorithm])],,
AC_DEFINE(ENABLE_WHIRLPOOL, 1, "Whirlpool Algorithm"))

AC_ARG_ENABLE([pkgconfig],
    [AS_HELP_STRING([--enable-pkgconfig],[generate pkg-config .pc file])])
AM_CONDITIONAL([ENABLE_PKGCONFIG], [test x"$enable_pkgconfig" = xyes])
PKG_INSTALLDIR

AC_CONFIG_FILES([Makefile
		 mhash.spec
		 include/Makefile
		 doc/Makefile
		 src/Makefile
		 lib/Makefile])
AC_OUTPUT
