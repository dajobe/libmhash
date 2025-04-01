# mhash #

Description
-----------

Mhash is a free (under GNU LGPL) library which provides a uniform
interface to a large number of hash algorithms. These algorithms can
be used to compute checksums, message digests, and other signatures.

Features
--------

The mhash library provides the following features:

* Free software (GNU Lesser General Public License)
* Reentrancy support
* Support for known strong algorithms
* Support for less-known algorithms such as GOST
* Should work on every ANSI C conforming platform

Hash Algorithms
---------------

The HMAC support implements the basics for message authentication,
following RFC 2104. In the later versions some key generation
algorithms, which use hash algorithms, have been added. The manpage
for mhash is
[mhash.3.html](http://mhash.sourceforge.net/mhash.3.html).

At the time of writing this, the library supports the algorithms:

SHA1, SHA160, SHA192, SHA224, SHA384, SHA512, HAVAL128, HAVAL160, HAVAL192, HAVAL224, HAVAL256, RIPEMD128, RIPEMD256, RIPEMD320, MD4, MD5, TIGER, TIGER128, TIGER160, ALDER32, CRC32, CRC32b, WHIRLPOOL, GOST, SNEFRU128, SNEFRU256

Mapping these to bitlengths, we can see:

| Algorithm | Output Bitlength |
| :-------- | :-- | :-- | :------ | :-- | :-- | :-- | :-- | :-- | :-- | :-- |
| **Name** | 32  | 32b | 128     | 160 | 192 | 224 | 256 | 320 | 384 | 512 |
| SHA       |     |     |         | 1   | Y   | Y   | Y   |     | Y   | Y   |
| HAVAL     |     |     | Y       | Y   | Y   | Y   | Y   |     |     |     |
| RIPEMD    |     |     | Y       |     |     |     | Y   | Y   |     |     |
| MD        |     |     | 2, 4, 5 |     |     |     |     |     |     |     |
| TIGER     |     |     | Y       | Y   | ONL |     |     |     |     |     |
| ALDER     | Y   |     |         |     |     |     |     |     |     |     |
| CRC       | Y   | Y   |         |     |     |     |     |     |     |     |
| WHIRLPOOL |     |     |         |     |     |     |     |     |     | ONL |
| GOST      |     |     |         |     |     |     |     |     |     | ONL |
| SNEFRU    |     |     | Y       |     |     |     | Y   |     |     |     |

Key:

Y : The name is suffixed by the bit-length  
Number : The name is suffixed by this number  
ONL : There is no suffix  
I : The hash is not secure at this length  
X : The hash has been padded and is not as strong as the bit-length suggests



Disclaimer
----------

Please read the file COPYING before using mhash.

Installation
------------

For installing mhash under Unix please read the document INSTALL.

New Versions
------------

Information on how to retrieve new versions of mhash can be found on
[https://mhash.sourceforge.net/](https://mhash.sourceforge.net/)

Credits
-------

Please read the file AUTHORS.

Sources
-------

* Original upstream development: git://git.code.sf.net/p/mhash/code
* Debian developer fork for pushing patched upstream: git://git.code.sf.net/u/bpearlmutter/mhash
* Debian packaging repository: git://anonscm.debian.org/collab-maint/mhash.git
 and Debian developer clone of that: git://github.com/barak/mhash
* Fedora mash repo git://pkgs.fedoraproject.org/mhash.git

Contacts
--------

[https://sourceforge.net/projects/mhash/lists/mhash-dev](https://sourceforge.net/projects/mhash/lists/mhash-dev)
