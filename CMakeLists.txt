cmake_minimum_required(VERSION 3.8)
SET (CMAKE_C_COMPILER_WORKS 1)
SET (CMAKE_CXX_COMPILER_WORKS 1)
project(redis)

set(CMAKE_CXX_STANDARD 11)

add_definitions(-D__clang__ -D_clang_ -Dclang -D__LINUX__)
include_directories(src)
include_directories(src/modules)
aux_source_directory(src SRC)
aux_source_directory(src/modules SRC_MODULES)

set(RRDIS_SRC
        src/adlist.c
        src/adlist.h
        src/ae.c
        src/ae.h
        src/ae_epoll.c
        src/ae_kqueue.c
        src/ae_select.c
        src/anet.c
        src/anet.h
        src/aof.c
        src/bio.c
        src/bio.h
        src/config.c
        src/config.h
        src/db.c
        src/debug.c
        src/dict.c
        src/dict.h
        src/endian.c
        src/endian.h
        src/epoll.h
        src/fmacros.h
        src/help.h
        src/intset.c
        src/intset.h
        src/lzf.h
        src/lzf_c.c
        src/lzf_d.c
        src/lzfP.h
        src/Makefile
        src/memtest.c
        src/mkreleasehdr.sh
        src/multi.c
        src/networking.c
        src/object.c
        src/pqsort.c
        src/pqsort.h
        src/pubsub.c
        src/rdb.c
        src/redis.c
        src/redis.h
        src/redis-benchmark.c
        src/redis-check-aof.c
        src/redis-check-dump.c
        src/redis-cli.c
        src/release.c
        src/replication.c
        src/sds.c
        src/sds.h
        src/sha1.c
        src/sha1.h
        src/slowlog.c
        src/slowlog.h
        src/solarisfixes.h
        src/sort.c
        src/syncio.c
        src/t_hash.c
        src/t_list.c
        src/t_set.c
        src/t_string.c
        src/t_zset.c
        src/testhelp.h
        src/util.c
        src/util.h
        src/valgrind.sup
        src/version.h
        src/vm.c
        src/ziplist.c
        src/ziplist.h
        src/zipmap.c
        src/zipmap.h
        src/zmalloc.c
        src/zmalloc.h
        )

add_executable(redis ${RRDIS_SRC} src/redis.c)