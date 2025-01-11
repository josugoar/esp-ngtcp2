set(srcs
    "nghttp3/lib/nghttp3_balloc.c"
    "nghttp3/lib/nghttp3_buf.c"
    "nghttp3/lib/nghttp3_conn.c"
    "nghttp3/lib/nghttp3_conv.c"
    "nghttp3/lib/nghttp3_debug.c"
    "nghttp3/lib/nghttp3_err.c"
    "nghttp3/lib/nghttp3_frame.c"
    "nghttp3/lib/nghttp3_gaptr.c"
    "nghttp3/lib/nghttp3_http.c"
    "nghttp3/lib/nghttp3_idtr.c"
    "nghttp3/lib/nghttp3_ksl.c"
    "nghttp3/lib/nghttp3_map.c"
    "nghttp3/lib/nghttp3_mem.c"
    "nghttp3/lib/nghttp3_objalloc.c"
    "nghttp3/lib/nghttp3_opl.c"
    "nghttp3/lib/nghttp3_pq.c"
    "nghttp3/lib/nghttp3_qpack.c"
    "nghttp3/lib/nghttp3_qpack_huffman.c"
    "nghttp3/lib/nghttp3_qpack_huffman_data.c"
    "nghttp3/lib/nghttp3_range.c"
    "nghttp3/lib/nghttp3_rcbuf.c"
    "nghttp3/lib/nghttp3_ringbuf.c"
    "nghttp3/lib/nghttp3_str.c"
    "nghttp3/lib/nghttp3_stream.c"
    "nghttp3/lib/nghttp3_tnode.c"
    "nghttp3/lib/nghttp3_unreachable.c"
    "nghttp3/lib/nghttp3_vec.c"
    "nghttp3/lib/nghttp3_version.c"
    "nghttp3/lib/sfparse/sfparse.c")

idf_component_register(SRCS "${srcs}"
                    INCLUDE_DIRS port/include nghttp3/lib/includes
                    PRIV_INCLUDE_DIRS port/private_include nghttp3/lib)

target_compile_options(${COMPONENT_LIB} PRIVATE "-Wno-format" "-Wno-maybe-uninitialized")
target_compile_definitions(${COMPONENT_LIB} PRIVATE "-DHAVE_CONFIG_H")
