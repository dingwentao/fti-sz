set(SRC_zlib
	adler32.c crc32.c deflate.c gzclose.c gzlib.c gzwrite.c inffast.c inffixed.h inflate.h inftrees.h trees.h zconf.h zutil.c
	compress.c crc32.h deflate.h gzguts.h gzread.c infback.c inffast.h inflate.c inftrees.c trees.c uncompr.c zlib.h zutil.h)

append_property(SOURCE ${SRC_zlib}
    PROPERTY COMPILE_FLAGS "-fPIC")

add_library(zlib OBJECT ${SRC_zlib})
